Get dynamic port range

    netsh int ipv4 show dynamicportrange tcp

Get all TCP connections

    netstat –ano –p tcp
    
Change dynamic port range (from 10000-65535)

    netsh int ipv4 set dynamicport tcp start=10000 num=55535

Change TcpTimedWaitDelay (Default 4 minutes)

    HKLM\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\TcpTimedWaitDelay
