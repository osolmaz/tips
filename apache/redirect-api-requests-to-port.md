# Maintaining a Unified Backend

When one has a configuration where the client code is served by Apache, and
the backend is provided as a server running on a different port, maintaining a nice
URL scheme might seem like a challenge.

The ideal solution is to present `/api` as an endpoint whose requests will be
forwarded to the API server.

First, find and uncomment the following lines on `/etc/httpd/conf/httpd.conf`

    # LoadModule proxy_module modules/mod_proxy.so
    # Include conf/extra/httpd-vhosts.conf

Then, add the following virtual host to
`/etc/httpd/conf/extra/httpd-vhosts.conf`.

    <VirtualHost *:80>
      ProxyPreserveHost On
      ProxyRequests Off
      ServerName dummy-host.example.com
      ServerAlias www.dummy-host.example.com
      ProxyPass /api/ http://localhost:5000/
      ProxyPassReverse /api/ http://localhost:5000/
    </VirtualHost>

The port number in the example above
is 5000. Change it and the server name and alias to suit your needs.
