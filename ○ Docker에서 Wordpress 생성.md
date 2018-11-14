# docker - wordpress

### ○ docker에서 wordpress 생성

1. #### docker, docker-compose 설치 for centos

   ```
   yum install docker
   yum install docker-compose
   ```

   ```dis
   Running transaction
     Installing : python34-libs-3.4.9-1.el7.x86_64                                                                                                   1/20 
     Installing : python34-3.4.9-1.el7.x86_64                                                                                                        2/20 
     Installing : python34-six-1.11.0-1.el7.noarch                                                                                                   3/20 
     Installing : python34-websocket-client-0.47.0-1.el7.noarch                                                                                      4/20 
     Installing : python34-backports-ssl_match_hostname-3.5.0.1-1.el7.noarch                                                                         5/20 
     Installing : python34-pysocks-1.6.8-5.el7.noarch                                                                                                6/20 
     Installing : python34-urllib3-1.19.1-4.el7.noarch                                                                                               7/20 
     Installing : python34-dockerpty-0.4.1-9.el7.noarch                                                                                              8/20 
     Installing : python34-docker-pycreds-0.2.1-1.el7.noarch                                                                                         9/20 
     Installing : python34-docopt-0.6.2-7.el7.noarch                                                                                                10/20 
     Installing : python34-idna-2.7-1.el7.noarch                                                                                                    11/20 
     Installing : python34-chardet-2.3.0-4.el7.noarch                                                                                               12/20 
     Installing : python34-requests-2.12.5-2.el7.noarch                                                                                             13/20 
     Installing : python34-docker-2.6.1-1.el7.noarch                                                                                                14/20 
     Installing : python34-texttable-1.4.0-1.el7.noarch                                                                                             15/20 
     Installing : python34-PyYAML-3.11-2.el7.x86_64                                                                                                 16/20 
     Installing : python34-cached_property-1.3.0-7.el7.noarch                                                                                       17/20 
     Installing : python34-jsonschema-2.5.1-3.el7.noarch                                                                                            18/20 
     Installing : python34-setuptools-19.6.2-3.el7.noarch                                                                                           19/20 
     Installing : docker-compose-1.18.0-2.el7.noarch                                                                                                20/20 
     Verifying  : python34-dockerpty-0.4.1-9.el7.noarch                                                                                              1/20 
     Verifying  : python34-urllib3-1.19.1-4.el7.noarch                                                                                               2/20 
     Verifying  : python34-requests-2.12.5-2.el7.noarch                                                                                              3/20 
     Verifying  : python34-backports-ssl_match_hostname-3.5.0.1-1.el7.noarch                                                                         4/20 
     Verifying  : python34-docopt-0.6.2-7.el7.noarch                                                                                                 5/20 
     Verifying  : python34-idna-2.7-1.el7.noarch                                                                                                     6/20 
     Verifying  : python34-chardet-2.3.0-4.el7.noarch                                                                                                7/20 
     Verifying  : python34-websocket-client-0.47.0-1.el7.noarch                                                                                      8/20 
     Verifying  : python34-six-1.11.0-1.el7.noarch                                                                                                   9/20 
     Verifying  : python34-texttable-1.4.0-1.el7.noarch                                                                                             10/20 
     Verifying  : python34-PyYAML-3.11-2.el7.x86_64                                                                                                 11/20 
     Verifying  : python34-3.4.9-1.el7.x86_64                                                                                                       12/20 
     Verifying  : python34-libs-3.4.9-1.el7.x86_64                                                                                                  13/20 
     Verifying  : python34-cached_property-1.3.0-7.el7.noarch                                                                                       14/20 
     Verifying  : python34-pysocks-1.6.8-5.el7.noarch                                                                                               15/20 
     Verifying  : python34-jsonschema-2.5.1-3.el7.noarch                                                                                            16/20 
     Verifying  : docker-compose-1.18.0-2.el7.noarch                                                                                                17/20 
     Verifying  : python34-docker-2.6.1-1.el7.noarch                                                                                                18/20 
     Verifying  : python34-docker-pycreds-0.2.1-1.el7.noarch                                                                                        19/20 
     Verifying  : python34-setuptools-19.6.2-3.el7.noarch                                                                                           20/20 
   
   Installed:
     docker-compose.noarch 0:1.18.0-2.el7                                                                                                                 
   
   Dependency Installed:
     python34.x86_64 0:3.4.9-1.el7                                                     python34-PyYAML.x86_64 0:3.11-2.el7                               
     python34-backports-ssl_match_hostname.noarch 0:3.5.0.1-1.el7                      python34-cached_property.noarch 0:1.3.0-7.el7                     
     python34-chardet.noarch 0:2.3.0-4.el7                                             python34-docker.noarch 0:2.6.1-1.el7                              
     python34-docker-pycreds.noarch 0:0.2.1-1.el7                                      python34-dockerpty.noarch 0:0.4.1-9.el7                           
     python34-docopt.noarch 0:0.6.2-7.el7                                              python34-idna.noarch 0:2.7-1.el7                                  
     python34-jsonschema.noarch 0:2.5.1-3.el7                                          python34-libs.x86_64 0:3.4.9-1.el7                                
     python34-pysocks.noarch 0:1.6.8-5.el7                                             python34-requests.noarch 0:2.12.5-2.el7                           
     python34-setuptools.noarch 0:19.6.2-3.el7                                         python34-six.noarch 0:1.11.0-1.el7                                
     python34-texttable.noarch 0:1.4.0-1.el7                                           python34-urllib3.noarch 0:1.19.1-4.el7                            
     python34-websocket-client.noarch 0:0.47.0-1.el7                                  
   
   Complete!
   ```

2. #### 디렉토리 생성

   ```
   mkdir wordpress
   ```

3. #### <u>docker-compose.yml</u> 파일 생성

```
version: '3'
services:
   db:
     image: mysql:5.7
     volumes:
       - db_data:/var/lib/mysql
     restart: always
     environment:
       MYSQL_ROOT_PASSWORD: somewordpress
       MYSQL_DATABASE: wordpress
       MYSQL_USER: wordpress
       MYSQL_PASSWORD: wordpress

   wordpress:
     depends_on:
       - db
     image: wordpress:latest
     ports:
       - "80:80"
     restart: always
     environment:
       WORDPRESS_DB_HOST: db:3306
       WORDPRESS_DB_USER: wordpress
       WORDPRESS_DB_PASSWORD: wordpress
volumes:
    db_data:
```



3. #### <u>**docker-compose up -d**</u>

```
TODO...,,,
```

