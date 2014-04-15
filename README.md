# ParallelCurl class

Class implements [curl_multi_* function family](php.net/manual/en/ref.curl.php)
with random user agent string generation

Example usage:

    $links = array(
        'http://link1.com',
        'http://link1.com/page1',
        'http://link1.com/page2'
    );

    $result = array();

    foreach (array_chunk($links, 2) as $chunk) {
        $pcurl = new ParallelCurl($chunk);
        $result[] = $pcurl->download();
    }

    print_r($result);
