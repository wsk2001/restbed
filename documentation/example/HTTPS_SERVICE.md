Overview
--------

'HTTPS(HTTP Secure)는 컴퓨터 네트워크를 통한 보안 통신을 위한 HTTP(Hypertext Transfer Protocol)의 확장으로 인터넷에서 널리 사용됩니다. HTTPS에서는 통신 프로토콜이 TLS(Transport Layer Security)로 암호화되거나 이전에는 그 전신인 SSL(Secure Sockets Layer)입니다. 따라서 이 프로토콜은 종종 TLS를 통한 HTTP 또는 SSL을 통한 HTTP라고도 합니다.' -- [Wikipedia](https://en.wikipedia.org/wiki/HTTPS)

Example
-------

```C++
#include <memory>
#include <cstdlib>
#include <restbed>

using namespace std;
using namespace restbed;

void get_method_handler( const shared_ptr< Session > session )
{
    session->close( OK, "Hello, World!", { { "Content-Length", "13" }, { "Connection", "close" } } );
}

int main( const int, const char** )
{
    auto resource = make_shared< Resource >( );
    resource->set_path( "/resource" );
    resource->set_method_handler( "GET", get_method_handler );
    
    auto ssl_settings = make_shared< SSLSettings >( );
    ssl_settings->set_http_disabled( true );
    ssl_settings->set_private_key( Uri( "file:///tmp/server.key" ) );
    ssl_settings->set_certificate( Uri( "file:///tmp/server.crt" ) );
    ssl_settings->set_temporary_diffie_hellman( Uri( "file:///tmp/dh768.pem" ) );
    
    auto settings = make_shared< Settings >( );
    settings->set_ssl_settings( ssl_settings );
    
    Service service;
    service.publish( resource );
    service.start( settings );
    
    return EXIT_SUCCESS;
}
```

Build
-----

> $ clang++ -o example example.cpp -l restbed -l ssl -l crypt

Execution
---------

> $ cd /tmp
>
> $ openssl genrsa -out server.key 1024
>
> $ openssl req -new -key server.key -out server.csr
>
> $ openssl x509 -req -days 3650 -in server.csr -signkey server.key -out server.crt
>
> $ openssl dhparam -out dh768.pem 768
> 
> $ sudo ./example
>
> $ curl -k -v -w'\n' -X GET 'https://localhost/resource'
