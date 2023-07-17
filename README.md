Restbed [![Unix Build Status](https://travis-ci.org/Corvusoft/restbed.svg?branch=master)](https://travis-ci.org/Corvusoft/restbed)
[![Windows Build Status](https://ci.appveyor.com/api/projects/status/75wqogaks13xp817/branch/master?svg=true)](https://ci.appveyor.com/project/corvusoft/restbed/branch/master)
=============================================================================================================================

---

Restbed는 모바일, 태블릿, 데스크톱 및 임베디드 프로덕션 환경을 대상으로 설계된 다양한 비즈니스 프로세스를 모델링할 수 있는 기능과 함께 HTTP를 통한 원활하고 안전한 통신이 필요한 애플리케이션을 구축하기 위한 포괄적이고 일관된 프로그래밍 모델입니다.

> NGINX를 회사 자체 제품 라인에 내장하는 것과 비슷합니다. -- 솔루션 아키텍트, Bellrock Technology

Features
--------

| Feature                                                                                                                                                                                                       | Description                                                                                                                                                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [WebSockets](https://github.com/wsk2001/restbed/blob/master/documentation/example/WEB_SOCKET.md)                                                                                                          | 단일 TCP 연결을 통한 전이중 통신 채널.                                                                                                                                                                                                                                     |
| [Server-Sent Events](https://github.com/wsk2001/restbed/blob/master/documentation/example/SERVER_SIDE_EVENTS.md)                                                                                          | Server-Sent Events는 텍스트 기반 이벤트 데이터(예: 서버에서 생성된 실시간 알림 또는 업데이트)의 효율적인 서버-클라이언트 스트리밍을 가능하게 합니다.                                                                                                                                           |
| [Comet](https://github.com/wsk2001/restbed/blob/master/documentation/example/HTTP_PERSISTENT_CONNECTION.md)                                                                                                    | 서버에서 클라이언트로 데이터를 푸시하기 위한 장기 HTTP 요청을 허용하는 긴 폴링 모델.                                                                                                                                                                                                      |
| [SSL/TLS](https://github.com/wsk2001/restbed/blob/master/documentation/example/HTTPS_SERVICE.md)                                                                                                          | 유선 통신을 통해 보안을 유지하여 개인 데이터를 온라인으로 전송할 수 있습니다.                                                                                                                                                                                                                     |
| [Session Management](https://github.com/wsk2001/restbed/blob/master/documentation/example/SESSION_MANAGER.md)                                                                                             | 사용자 지정 HTTP 세션 지속성 및 관리 논리를 만듭니다.                                                                                                                                                                                                                                         |
| [HTTP Pipelining](https://github.com/wsk2001/restbed/blob/master/documentation/example/HTTP_PIPELINING.md)                                                                                                | 해당 응답을 기다리지 않고 단일 TCP 연결에서 여러 HTTP 요청을 보낼 수 있는 기술입니다.                                                                                                                                                                   |
| [Path Parameters](https://github.com/wsk2001/restbed/blob/master/documentation/example/PATH_PARAMETERS.md)                                                                                                | 리소스 키, 개정 등과 같은 사용자 정의 경로 매개변수로 URI에 주석을 답니다.                                                                                                                                                                                                                   |
| 쿼리 매개변수                                                                                                                                                                                              | 자동화된 쿼리 매개변수 구문 분석.                                                                                                                                                                                                                                                                  |
| [Header Filters](https://github.com/wsk2001/restbed/blob/master/documentation/example/RESOURCE_FILTERING.md)                                                                                              | 들어오는 HTTP 요청을 헤더별로 필터링합니다.                                                                                                                                                                                                                                                            |
| [Logging](https://github.com/wsk2001/restbed/blob/master/documentation/example/LOGGING.md)                                                                                                                | 로그 항목이 생성되는 방법과 위치를 사용자 지정합니다.                                                                                                                                                                                                                                                     |
| [Multi-Path Resources](https://github.com/wsk2001/restbed/blob/master/documentation/example/MULTIPATH_RESOURCES.md)                                                                            | 가독성 향상을 위해 리소스에 다중 경로를 제공합니다.                                                                                                                                                                                                                                             |
| [Customisable Methods](https://github.com/wsk2001/restbed/blob/master/documentation/example/CUSTOM_HTTP_METHOD.md)                                                                                            | 사용자 지정 HTTP 메서드 추가                                                                                                                                                                                                                                                                    |
| [Compression](https://github.com/wsk2001/restbed/blob/master/documentation/example/COMPRESSION.md)                                                                                                        | 모든 형태의 압축 GZip, Deflate 등을 처리할 수 있는 적응성...                                                                                                                                                                                                                               |
| Encoding                                                                                                                                                                                                      | UTF-32, ASCII 등 모든 형식의 인코딩을 처리할 수 있는 적응성...                                                                                                                                                                                                                                 |
| [Rules Engine](https://github.com/wsk2001/restbed/blob/master/documentation/example/RULES_ENGINE.md)                                                                                                      | 읽을 수 있는 코드 단위로 들어오는 요청을 처리하여 복잡성을 줄입니다.                                                                                                                                                                                                                      |
| [HTTP](https://github.com/wsk2001/restbed/blob/master/documentation/example/HTTP_CLIENT.md)/[HTTPS](https://github.com/wsk2001/restbed/blob/master/example/https_client/source/verify_none.cpp) | 선택적 SSL 피어 인증서 확인 기능이 내장된 클라이언트 기능. 더 이상 사용되지 않음                                                                                                                                                                                                                      |
| IPv4/IPv6                                                                                                                                                                                                     | 인터넷 프로토콜 버전 4/6 네트워크 지원.                                                                                                                                                                                                                                                       |
| Architecture                                                                                                                                                                                                  | Asynchronous [single](https://github.com/wsk2001/restbed/blob/master/example/publishing_resources/source/example.cpp) or [multi-threaded](https://github.com/wsk2001/restbed/blob/master/documentation/example/MULTITHREADED_SERVICE.md) C10K 문제를 해결할 수 있는 아키텍처입니다. |
| 변환기                                                                                                                                                                                                    | 기본 데이터 유형에 대한 기본 제공 경로, 쿼리 및 헤더 변환.                                                                                                                                                                                                                                 |
| [Authentication](https://github.com/wsk2001/restbed/blob/master/documentation/example/DIGEST_AUTHENTICATION.md)                                                                                                  | 별도의 서비스 및/또는 리소스 수준 인증.                                                                                                                                                                                                                                               |
| [Error Handling](https://github.com/wsk2001/restbed/blob/master/documentation/example/ERROR_HANDLING.md)                                                                                                  | 별도의 서비스 및/또는 리소스 수준 오류 처리.                                                                                                                                                                                                                                               |
| [Address Binding](https://github.com/wsk2001/restbed/blob/master/documentation/example/ADDRESS_BINDING.md)                                                                                           | HTTP 및/또는 HTTPS 서비스를 별도의 IP 주소에 바인딩합니다.                                                                                                                                                                                                                                           |
| [Signal Handling](https://github.com/wsk2001/restbed/blob/master/documentation/example/SIGNAL_HANDLING.md)                                                                                                | OS에서 생성된 프로세스 신호를 캡처합니다.                                                                                                                                                                                                                                                                |
| [Documentation](https://github.com/wsk2001/restbed/tree/master/documentation)                                                                                                                               | 아키텍처 및 API를 다루는 고품질 문서입니다.                                                                                                                                                                                                                                        |
| Compliance                                                                                                                                                                                                    | HTTP 1.0/1.1+ 규정 준수를 처리할 수 있는 유연성.                                                                                                                                                                                                                                                    |
| Mature                                                                                                                                                                                                        | 2013년부터 안전하고 안정적이며 광범위한 테스트를 거쳤습니다.                                                                                                                                                                                                                                                   |
| Community                                                                                                                                                                                                     | 활동적이고 활기차고 활기찬 오픈 소스 커뮤니티.                                                                                                                                                                                                                                                 |
| Support                                                                                                                                                                                                       | 상업적 지원은 [Corvusoft](http://www.corvusoft.co.uk).                                                                                                                                                                                                                        |

Example
-------

```C++
#include <memory>
#include <cstdlib>
#include <restbed>

using namespace std;
using namespace restbed;

void post_method_handler( const shared_ptr< Session > session )
{
    const auto request = session->get_request( );

    int content_length = request->get_header( "Content-Length", 0 );

    session->fetch( content_length, [ ]( const shared_ptr< Session > session, const Bytes & body )
    {
        fprintf( stdout, "%.*s\n", ( int ) body.size( ), body.data( ) );
        session->close( OK, "Hello, World!", { { "Content-Length", "13" } } );
    } );
}

int main( const int, const char** )
{
    auto resource = make_shared< Resource >( );
    resource->set_path( "/resource" );
    resource->set_method_handler( "POST", post_method_handler );

    auto settings = make_shared< Settings >( );
    settings->set_port( 1984 );
    settings->set_default_header( "Connection", "close" );

    Service service;
    service.publish( resource );
    service.start( settings );

    return EXIT_SUCCESS;
}
```

More in-depth examples can be found [here](https://github.com/Corvusoft/restbed/tree/master/documentation/example). To see Restbed used in anger, please visit Corvusoft's [RestQ](https://github.com/corvusoft/restq) project.

License
-------

&copy; 2013-2020 Corvusoft Limited, United Kingdom. All rights reserved.

The Restbed framework is dual licensed; See [LICENSE](LICENSE) for full details.

Support
-------

Please contact sales@corvusoft.co.uk, for support and licensing options including bespoke software development, testing, design consultation, training, mentoring and code review.

Please submit all enhancements, proposals, and defects via the [issue](http://github.com/corvusoft/restbed/issues) tracker; Alternatively ask a question on [StackOverflow](http://stackoverflow.com/questions/ask) tagged [#restbed](http://stackoverflow.com/questions/tagged/restbed).

Build 
-----

```bash
git clone --recursive https://github.com/corvusoft/restbed.git
mkdir restbed/build
cd restbed/build
cmake [-DBUILD_SSL=NO] [-DBUILD_TESTS=NO] ..
make install
make test
```

You will now find all required components installed in the distribution sub-folder.

Building with external libraries
--------------------------------

If you wish to build with external libraries (OpenSSL, ASIO).

```bash
git clone https://github.com/corvusoft/restbed.git
mkdir restbed/build
cd restbed/build
cmake [-DBUILD_SSL=NO] [-DBUILD_TESTS=NO] ..
make install
make test
```

Windows Build Instructions
--------------------------

For Microsoft Visual Studio instructions please see feature [#17](https://github.com/Corvusoft/restbed/issues/17).

Building restbed - Using vcpkg
------------------------------

You can download and install restbed using the [vcpkg](https://github.com/Microsoft/vcpkg) dependency manager:

    git clone https://github.com/Microsoft/vcpkg.git
    cd vcpkg
    ./bootstrap-vcpkg.sh
    ./vcpkg integrate install
    ./vcpkg install restbed

The restbed port in vcpkg is kept up to date by Microsoft team members and community contributors. If the version is out of date, please [create an issue or pull request](https://github.com/Microsoft/vcpkg) on the vcpkg repository.


Documentation
-------------

This codebase is intended to be as self documenting as possible. We have supplied many [examples](https://github.com/Corvusoft/restbed/tree/master/documentation/example) and [test suites](https://github.com/corvusoft/restbed/tree/master/test) to help aid developers.

You can locate the latest design and API documentation [here](https://github.com/Corvusoft/restbed/tree/master/documentation).

Minimum Requirements
--------------------

| Resource | Requirement                                     |
|:--------:|:-----------------------------------------------:|
| Compiler |            C++14 compliant or above             |
|    OS    | BSD, Linux, Mac OSX, Windows, Raspbian          |

Road Map
--------

| Milestone                                                                           | Feature                                 | Status      |
|:-----------------------------------------------------------------------------------:|:---------------------------------------:|:-----------:|
|                                         0.0                                         |        Asynchronous HTTP Service        |  complete   |
|                                         1.0                                         |           HTTP 1.0 Compliance           |  complete   |
|                                         2.0                                         |           HTTP 1.1 Compliance           |  complete   |
|                                         2.5                                         |           Secure Socket Layer           |  complete   |
|                                         2.5                                         | Simultaneous Network Ports (HTTP/HTTPS) |  complete   |
|                                         3.0                                         |              Rules Engine               |  complete   |
| [3.5](https://github.com/Corvusoft/restbed/issues?utf8=%E2%9C%93&q=milestone%3A3.5) |   Schedule Tasks on Service run-loop    |  complete   |
| [3.5](https://github.com/Corvusoft/restbed/issues?utf8=%E2%9C%93&q=milestone%3A3.5) |    Multi-Threaded service capability    |  complete   |
| [3.5](https://github.com/Corvusoft/restbed/issues?utf8=%E2%9C%93&q=milestone%3A3.5) |    Bind Service to specific Address     |  complete   |
| [3.5](https://github.com/Corvusoft/restbed/issues?utf8=%E2%9C%93&q=milestone%3A3.5) |           Session Management            |  complete   |
|             [4.0](https://github.com/Corvusoft/restbed/milestones/4.0)              |               HTTP Client               |  complete   |
|             [4.0](https://github.com/Corvusoft/restbed/milestones/4.0)              |             Signal Handling             |  complete   |
|             [4.5](https://github.com/Corvusoft/restbed/milestones/4.5)              |            API Documentation            |  complete   |
|             [4.5](https://github.com/Corvusoft/restbed/milestones/4.5)              |               Web Sockets               |  complete   |
|             [5.0](https://github.com/Corvusoft/restbed/milestones/5.0)              |      Client-side SSL certificates       | development |
|             [5.0](https://github.com/Corvusoft/restbed/milestones/5.0)              |            Resource Caching             | development |
|             [5.0](https://github.com/Corvusoft/restbed/milestones/5.0)              |          Runtime Modifications          | development |
|             [5.0](https://github.com/Corvusoft/restbed/milestones/5.0)              |            HTTP 2 compliance            | development |
|             [5.0](https://github.com/Corvusoft/restbed/milestones/5.0)              |         Refactor, Reduce, Reuse         |   pending   |

Contact
-------

| Method                                      | Description                                 |
|:--------------------------------------------|:--------------------------------------------|
| [Twitter](http://www.twitter.com/corvusoft) | Tweet us your questions & feature requests. |
| support@corvusoft.co.uk                     | Support related queries.                    |
| sales@corvusoft.co.uk                       | Sale related queries.                       |
