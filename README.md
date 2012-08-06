Description
-----------
    php ext
    tags: C, php, php-ext.
    Create time: 2012.08

Usage
-----
    1. cd src/php-5.3.5/ext
    2. mkdir bdipmap     或者 ./ext_skel --extname=bdipmap
    3. cp -r svn/bdipmap/* bdipmap/
    4. cd bdipmap
    5. phpize
    6. ./configure --enable-bdipmap
    7. make
    8. cp modules/bdipmap.so php-extension/
    9. vi php.ini
    +[bdipmap]
    +extension=bdipmap.so
    +bdipmap.data_path = "./data/ip.map"
    9. WEBSERVICE restart
    10. test
    vi test_bdipmap.php
    <?php
    echo dbipmap_debug('debug for test');
    echo 'get region by user ip: ' . bdipmap_search_map(123765); 

    $ip = '127.0.0.1';
    $ip_long = sprintf('%u', ip2long($ip));
    echo '(long int)' . $ip . ' = ' . $ip_long;
    ?>
