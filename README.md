# Pluginsdc
$url = "http://thecollectorsindex.neowebservices.co.uk";
$input = @file_get_contents($url) or die("Could not access file: $url");
$regexp = "<a\s[^>]*href=(\"??)([^\" >]*?)\\1[^>]*>(.*)<\/a>";
if (preg_match_all("/$regexp/siU", $input, $matches)) {
    echo '<pre>';
    print_r($matches);
    echo '</pre>';
}
