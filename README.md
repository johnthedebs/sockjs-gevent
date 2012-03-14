gevent-sockjs
=============

A work in progress gevent server backend for SockJS.
General goal is to have a faithful implemention of @majek's
[sockjs-protocol](https://github.com/sockjs/sockjs-protocol)
that plays nicely with gevent & green threads.

Somewhat unstable at the moment, does not pass all sockjs-protocol tests.

Running
=======

    # New virtualenv
    mkvirtualenv sockjs

    # To run the dev server
    pip install -r requirements.txt
    python gevent_sockjs/devserver.py

    # To run tests
    pip install -r requirements_dev.txt
    nosetests

Test Status
===========

    test_greeting (test_protocol.BaseUrlGreeting) ... ok
    test_notFound (test_protocol.BaseUrlGreeting) ... ok
    test_response_limit (test_protocol.EventSource) ... ok
    test_transport (test_protocol.EventSource) ... ok
    test_abort_xhr_polling (test_protocol.HandlingClose) ... ok
    test_abort_xhr_streaming (test_protocol.HandlingClose) ... ok
    test_close_frame (test_protocol.HandlingClose) ... FAIL
    test_close_request (test_protocol.HandlingClose) ... ok
    test_no_callback (test_protocol.HtmlFile) ... ok
    test_response_limit (test_protocol.HtmlFile) ... ok
    test_transport (test_protocol.HtmlFile) ... ok
    test_cacheability (test_protocol.IframePage) ... ok
    test_invalidUrl (test_protocol.IframePage) ... ok
    test_queriedUrl (test_protocol.IframePage) ... ok
    test_simpleUrl (test_protocol.IframePage) ... ok
    test_versionedUrl (test_protocol.IframePage) ... ok
    test_basic (test_protocol.InfoTest) ... ok
    test_disabled_websocket (test_protocol.InfoTest) ... ok
    test_entropy (test_protocol.InfoTest) ... ok
    test_options (test_protocol.InfoTest) ... ok
    test_xhr_server_decodes (test_protocol.JSONEncoding) ... ok
    test_xhr_server_encodes (test_protocol.JSONEncoding) ... ok
    test_content_types (test_protocol.JsonPolling) ... ok
    test_invalid_json (test_protocol.JsonPolling) ... ok
    test_no_callback (test_protocol.JsonPolling) ... ok
    test_transport (test_protocol.JsonPolling) ... ok
    test_closeSession (test_protocol.Protocol) ... ok
    test_simpleSession (test_protocol.Protocol) ... ok
    test_close (test_protocol.RawWebsocket) ... ERROR
    test_transport (test_protocol.RawWebsocket) ... ERROR
    test_anyValue (test_protocol.SessionURLs) ... ok
    test_ignoringServerId (test_protocol.SessionURLs) ... ok
    test_invalidPaths (test_protocol.SessionURLs) ... ok
    test_broken_json (test_protocol.WebsocketHixie76) ... ERROR
    test_close (test_protocol.WebsocketHixie76) ... ERROR
    test_empty_frame (test_protocol.WebsocketHixie76) ... FAIL
    test_headersSanity (test_protocol.WebsocketHixie76) ... ok
    test_reuseSessionId (test_protocol.WebsocketHixie76) ... ERROR
    test_transport (test_protocol.WebsocketHixie76) ... ok
    test_httpMethod (test_protocol.WebsocketHttpErrors) ... ok
    test_invalidConnectionHeader (test_protocol.WebsocketHttpErrors) ... ok
    test_invalidMethod (test_protocol.WebsocketHttpErrors) ... ok
    test_verifyOrigin (test_protocol.WebsocketHttpErrors) ... ok
    test_broken_json (test_protocol.WebsocketHybi10) ... ERROR
    test_close (test_protocol.WebsocketHybi10) ... ERROR
    test_firefox_602_connection_header (test_protocol.WebsocketHybi10) ... ERROR
    test_headersSanity (test_protocol.WebsocketHybi10) ... ERROR
    test_transport (test_protocol.WebsocketHybi10) ... ERROR
    test_content_types (test_protocol.XhrPolling) ... ok
    test_invalid_json (test_protocol.XhrPolling) ... ok
    test_invalid_session (test_protocol.XhrPolling) ... ok
    test_jsessionid (test_protocol.XhrPolling) ... ok
    test_options (test_protocol.XhrPolling) ... ok
    test_transport (test_protocol.XhrPolling) ... ok
    test_options (test_protocol.XhrStreaming) ... ok
    test_response_limit (test_protocol.XhrStreaming) ... ok
    test_transport (test_protocol.XhrStreaming) ... ok

Test Coverage
=============

    Name                        Stmts   Miss  Cover
    -----------------------------------------------
    gevent_sockjs/errors           21     13    38%
    gevent_sockjs/handler         211    175    17%
    gevent_sockjs/protocol         56     26    54%
    gevent_sockjs/router           87     53    39%
    gevent_sockjs/server           53     25    53%
    gevent_sockjs/session          73     45    38%
    gevent_sockjs/sessionpool      58     42    28%
    gevent_sockjs/static           37     25    32%
    gevent_sockjs/transports      102     62    39%
    -----------------------------------------------
    TOTAL                         698    466    33%
