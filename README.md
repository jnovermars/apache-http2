# apache-http2
Installation HTTP/2 on Apache2.4.18, OS: Ubuntu 16.04.1 LTS 

# Requirements
This wil only work on Ubuntu 16.04 and 16.04.1 with apache 2.4.18 other versions are not tested !

# Run
Check out this git repo and run the install_apache2_http2.sh

Or Run (wget is required):

    sudo apt install -y wget 
    mkdir /tmp/apache2-build
    cd /tmp/apache2-build
    wget https://raw.githubusercontent.com/xleeuwx/apache-http2/master/install_apache2_http2.sh -O /tmp/apache2-build/install_apache2_http2.sh
    sudo chmod +x install_apache2_http2.sh
    sudo bash install_apache2_http2.sh
    
# Enable HTTP/2

Add this to your vhost file bellow the ServerName:
    
    ...
    ServerName www.example.com
    ServerAdmin test@example.com
        
    # for https with fallback to http and http/1.1
    Protocols h2 h2c http/1.1
      
    # for a https server
    Protocols h2 http/1.1
      
    # for a http server
    Protocols h2c http/1.1
      
    ErrorLog /var/log/www.example.com.error
    ...
    
    
# Bugs ?
If you find a bug please go to the issue tracker.