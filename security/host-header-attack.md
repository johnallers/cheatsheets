    curl -H "Host: badhost.net" https://target.com/Login.aspx -k | fgrep badhost

    curl -H "Host: badhost.net" https://target.com/Login.aspx -k -X POST -H "Content-Type: application/json" -d "myparams"
