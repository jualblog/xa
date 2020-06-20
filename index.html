<?php
//settings
$cache_ext  = '.html'; //file extension
$cache_time     = 43200;  //Cache file expires after these seconds (1 hour = 3600 sec) (8 hour = 28800 sec) (12 hour = 43200 sec)
$cache_folder   = 'cache/'; //folder to store Cache files
$ignore_pages   = array('', '');

$dynamic_url    = 'http://'.$_SERVER['HTTP_HOST'] . $_SERVER['REQUEST_URI'] . $_SERVER['QUERY_STRING']; // requested dynamic page (full url)
$cache_file     = $cache_folder.md5($dynamic_url).$cache_ext; // construct a cache file
$ignore = (in_array($dynamic_url,$ignore_pages))?true:false; //check if url is in ignore list

if (!$ignore && file_exists($cache_file) && time() - $cache_time < filemtime($cache_file)) { //check Cache exist and it's not expired.
    ob_start('ob_gzhandler'); //Turn on output buffering, "ob_gzhandler" for the compressed page with gzip.
    readfile($cache_file); //read Cache file
    echo '<!-- cached page - '.date('l jS \of F Y h:i:s A', filemtime($cache_file)).', Page : '.$dynamic_url.' -->';
    ob_end_flush(); //Flush and turn off output buffering
    exit(); //no need to proceed further, exit the flow.
}
//Turn on output buffering with gzip compression.
ob_start('ob_gzhandler');

require_once('siteconfig.php');
require_once('url_slug.php'); 
?>
<!doctype html>
<html>
    <head><meta http-equiv="Content-Type" content="text/html; charset=utf-8">
		<!-- Meta -->
		
		<meta name="viewport" content="width=device-width">
		<title><?php echo $homepage_title; ?></title>
		<meta name="description" content="<?php echo $homepage_desc; ?>" />
		<meta name="keywords" content="<?php echo $site_keywords; ?>" />
		<meta property="og:site_name" content="<?php echo $site_title; ?>"/>
		<meta property="og:type" content="website"/>
		<meta property="og:title" content="<?php echo $homepage_title; ?>"/>
		<meta property="og:description" content="<?php echo $homepage_desc; ?>"/>
		<!-- CSS and Scripts -->
		<?php include 'includes/headscripts.php'; ?>
		<script type="text/javascript" src="<?php echo $site_url;?>/js/jquery.jcarousel.min.js"></script>
		<?php include 'ads/head_code.php'; ?>
    </head>
<body>
<?php include 'includes/header.php'; ?>
<script>
jQuery(document).ready(function($){
if(jQuery().jcarousel) {
	// Featured Carousel - Horizontal 
	$(window).bind('load resize', function(){
		
		$('.fcarousel-6').deCarousel();
		$('.fcarousel-5').deCarousel();
	});
	// games carousel
	$('.jcarousel').jcarousel({
        wrap: 'circular'
    });
	$('.jcarousel').jcarouselAutoscroll({
	target: '+=3',
	interval: 4000,
    autostart: true
	});
		
	// Featured Carousel - Vertical 
	$('.carousel-clip').jcarousel({
		vertical: true,
		wrap: 'circular'
	});
	$('.carousel-prev').jcarouselControl({target: '-=4'});
	$('.carousel-next').jcarouselControl({target: '+=4'});
}
});
</script>
<div class="scrollback">
<div class="container">
<div class="scrollcontent">
<div class="carousel fcarousel fcarousel-6">
<div class="scrolltitle">
<h1><?php echo $home_carousel_title; ?></h1>
</div>
<div class="carousel-container">
<div class="jcarousel">
<ul>
<?php
if (!empty($homeapps_genre_id)) {
$string = file_get_contents('https://itunes.apple.com/'.$site_country.'/rss/topmovies/limit=10/genre='.$home_genre_id.'/xml');
}
else {
$string = file_get_contents('https://itunes.apple.com/'.$site_country.'/rss/topmovies/limit=10/xml');
}
$string = preg_replace("/(<\/?)(\w+):([^>]*>)/", "$1$2$3", $string);
$xml = simplexml_load_string($string);

// Output
$rssresults = '';

foreach ($xml->entry as $val) {
    
	// edit foreach
	$musicid = $val->id;
	$musicid = str_replace("/id/","xxx",$musicid);
	$musicid=explode('/id',$musicid);
	$musicid=explode('?',$musicid[1]);
	// ssl images width="180px" height="180px"
	$sslimage = preg_replace('/http/ms', "http", $val->imimage[2]);
	$sslimage = preg_replace('/.mzstatic/ms', ".mzstatic", $sslimage);
	$bigimage = preg_replace('/170x170/ms', "300x300", $sslimage);
	// remove year from title
	$val->imname = preg_replace('@\(.*?\)@', '', $val->imname);
    $rssresults .= '<li><div class="homethumb"><a href="'.$site_url.'/movie/'.$musicid[0].'/'.cano($val->imname).'"><img data-src="'.$bigimage.'" src="'.$site_url.'/images/loading.svg" alt=""><span class="overlay"><p>'.$val->imname.'</p></span></a></div></li>';
		
   
}
echo $rssresults;

?>
</ul>
</div><!-- end .jcarousel -->
<div class="carousel-prev"></div>
<div class="carousel-next"></div>
</div><!-- end .carousel-container -->
</div><!-- end .carousel -->
</div><!-- end .scrollcontent -->
</div><!-- end .container -->
</div><!-- end .scrollback -->
<div class="homeframe">
<div class="container" style="margin-bottom:20px;">
<div class="pagetitle" style="margin-bottom:20px;">
<h1><?php echo $featapps_title;?></h1>
</div>
<?php 
$data = file_get_contents('https://itunes.apple.com/lookup?id='.$feat_id1.'&media=movie&entity=movie&country='.$site_country.'');
$response = json_decode($data);

$artist_title = $response->results[0]->artistName;
$sslimage = preg_replace('/http/ms', "http", $response->results[0]->artworkUrl100);
$sslimage = preg_replace('/.mzstatic/ms', ".mzstatic", $sslimage);
$main_image = preg_replace('/100x100bb.jpg/ms', "250x250bb.jpg", $sslimage);
// remove year from title
$response->results[0]->trackName = preg_replace('@\(.*?\)@', '', $response->results[0]->trackName);
?>
<div class="col-md-12" style="padding: 0px;">
<div class="featbox box1">
<div class="featimage">
<a href="<?php echo $site_url;?>/movie/<?php echo $response->results[0]->trackId;?>/<?php echo cano($response->results[0]->trackName);?>"><img data-src="<?php echo $main_image?>" src="<?php echo $site_url?>/images/loading.svg" alt="<?php echo $response->results[0]->trackName;?>"></a>

</div>
<h3><?php echo $response->results[0]->trackName;?></h3>
<h4><?php echo $byartist_mpage?> <?php echo $artist_title;?></h4>
<ul style="list-style:none;padding: 0px;">
<li><b><?php echo $release_mpage;?>:</b> <?php echo substr($response->results[0]->releaseDate,0,10);?></li>
<li><b><?php echo $cat_mpage;?>:</b> <?php echo $response->results[0]->primaryGenreName;?></li>
</ul>
<p>
<?php $feat_descr = strip_tags($response->results[0]->longDescription); ?>
<?php echo substr($feat_descr,0,530); ?>...
</p>
<a href="<?php echo $site_url;?>/movie/<?php echo $response->results[0]->trackId;?>/<?php echo cano($response->results[0]->trackName);?>" style="margin-right: 10px;" class="btn btn-raised btn-warning"><?php echo $rmore_title;?></a>
</div>
</div>
<!--end col-md-12 -->

<?php 
$data = file_get_contents('https://itunes.apple.com/lookup?id='.$feat_id2.'&media=movie&entity=movie&country='.$site_country.'');
$response = json_decode($data);

$artist_title = $response->results[0]->artistName;
$sslimage = preg_replace('/http/ms', "http", $response->results[0]->artworkUrl100);
$sslimage = preg_replace('/.mzstatic/ms', ".mzstatic", $sslimage);
$main_image = preg_replace('/100x100bb.jpg/ms', "250x250bb.jpg", $sslimage);
// remove year from title
$response->results[0]->trackName = preg_replace('@\(.*?\)@', '', $response->results[0]->trackName);
?>
<div class="col-md-12" style="padding: 0px;">
<div class="featbox box2">
<div class="featimage">
<a href="<?php echo $site_url;?>/movie/<?php echo $response->results[0]->trackId;?>/<?php echo cano($response->results[0]->trackName);?>"><img data-src="<?php echo $main_image?>" src="<?php echo $site_url?>/images/loading.svg" alt="<?php echo $response->results[0]->trackName;?>"></a>

</div>
<h3><?php echo $response->results[0]->trackName;?></h3>
<h4><?php echo $byartist_mpage?> <?php echo $artist_title;?></h4>
<ul style="list-style:none;padding: 0px;">
<li><b><?php echo $release_mpage;?>:</b> <?php echo substr($response->results[0]->releaseDate,0,10);?></li>
<li><b><?php echo $cat_mpage;?>:</b> <?php echo $response->results[0]->primaryGenreName;?></li>
</ul>
<p>
<?php $feat_descr = strip_tags($response->results[0]->longDescription); ?>
<?php echo substr($feat_descr,0,530); ?>...
</p>
<a href="<?php echo $site_url;?>/movie/<?php echo $response->results[0]->trackId;?>/<?php echo cano($response->results[0]->trackName);?>" style="margin-right: 10px;" class="btn btn-raised btn-warning"><?php echo $rmore_title;?></a>
</div>
</div>
<!--end col-md-12 -->

<?php 
$data = file_get_contents('https://itunes.apple.com/lookup?id='.$feat_id3.'&media=movie&entity=movie&country='.$site_country.'');
$response = json_decode($data);

$artist_title = $response->results[0]->artistName;
$sslimage = preg_replace('/http/ms', "http", $response->results[0]->artworkUrl100);
$sslimage = preg_replace('/.mzstatic/ms', ".mzstatic", $sslimage);
$main_image = preg_replace('/100x100bb.jpg/ms', "250x250bb.jpg", $sslimage);
// remove year from title
$response->results[0]->trackName = preg_replace('@\(.*?\)@', '', $response->results[0]->trackName);
?>
<div class="col-md-12" style="padding: 0px;">
<div class="featbox box3">
<div class="featimage">
<a href="<?php echo $site_url;?>/movie/<?php echo $response->results[0]->trackId;?>/<?php echo cano($response->results[0]->trackName);?>"><img data-src="<?php echo $main_image?>" src="<?php echo $site_url?>/images/loading.svg" width="180px" height="180px" alt="<?php echo $response->results[0]->trackName;?>"></a>
</div>
<h3><?php echo $response->results[0]->trackName;?></h3>
<h4><?php echo $byartist_mpage?> <?php echo $artist_title;?></h4>
<ul style="list-style:none;padding: 0px;">
<li><b><?php echo $release_mpage;?>:</b> <?php echo substr($response->results[0]->releaseDate,0,10);?></li>
<li><b><?php echo $cat_mpage;?>:</b> <?php echo $response->results[0]->primaryGenreName;?></li>
</ul>
<p>
<?php $feat_descr = strip_tags($response->results[0]->longDescription); ?>
<?php echo substr($feat_descr,0,530); ?>...
</p>
<a href="<?php echo $site_url;?>/movie/<?php echo $response->results[0]->trackId;?>/<?php echo cano($response->results[0]->trackName);?>" style="margin-right: 10px;" class="btn btn-raised btn-warning"><?php echo $rmore_title;?></a>
</div>
</div>
<!--end col-md-12 -->

<?php 
$data = file_get_contents('https://itunes.apple.com/lookup?id='.$feat_id4.'&media=movie&entity=movie&country='.$site_country.'');
$response = json_decode($data);

$artist_title = $response->results[0]->artistName;
$sslimage = preg_replace('/http/ms', "http", $response->results[0]->artworkUrl100);
$sslimage = preg_replace('/.mzstatic/ms', ".mzstatic", $sslimage);
$main_image = preg_replace('/100x100bb.jpg/ms', "250x250bb.jpg", $sslimage);
// remove year from title
$response->results[0]->trackName = preg_replace('@\(.*?\)@', '', $response->results[0]->trackName);
?>
<div class="col-md-12" style="padding: 0px;">
<div class="featbox box4">
<div class="featimage">
<a href="<?php echo $site_url;?>/movie/<?php echo $response->results[0]->trackId;?>/<?php echo cano($response->results[0]->trackName);?>"><img data-src="<?php echo $main_image?>" src="<?php echo $site_url?>/images/loading.svg" width="180px" height="180px" alt="<?php echo $response->results[0]->trackName;?>"></a>
</div>
<h3><?php echo $response->results[0]->trackName;?></h3>
<h4><?php echo $byartist_mpage?> <?php echo $artist_title;?></h4>
<ul style="list-style:none;padding: 0px;">
<li><b><?php echo $release_mpage;?>:</b> <?php echo substr($response->results[0]->releaseDate,0,10);?></li>
<li><b><?php echo $cat_mpage;?>:</b> <?php echo $response->results[0]->primaryGenreName;?></li>
</ul>
<p>
<?php $feat_descr = strip_tags($response->results[0]->longDescription); ?>
<?php echo substr($feat_descr,0,530); ?>...
</p>
<a href="<?php echo $site_url;?>/movie/<?php echo $response->results[0]->trackId;?>/<?php echo cano($response->results[0]->trackName);?>" style="margin-right: 10px;" class="btn btn-raised btn-warning"><?php echo $rmore_title;?></a>
</div>
</div>
<!--end col-md-12 -->

<?php 
$data = file_get_contents('https://itunes.apple.com/lookup?id='.$feat_id5.'&media=movie&entity=movie&country='.$site_country.'');
$response = json_decode($data);

$artist_title = $response->results[0]->artistName;
$sslimage = preg_replace('/http/ms', "http", $response->results[0]->artworkUrl100);
$sslimage = preg_replace('/.mzstatic/ms', ".mzstatic", $sslimage);
$main_image = preg_replace('/100x100bb.jpg/ms', "250x250bb.jpg", $sslimage);
// remove year from title
$response->results[0]->trackName = preg_replace('@\(.*?\)@', '', $response->results[0]->trackName);
?>
<div class="col-md-12" style="padding: 0px;">
<div class="featbox box2">
<div class="featimage">
<a href="<?php echo $site_url;?>/movie/<?php echo $response->results[0]->trackId;?>/<?php echo cano($response->results[0]->trackName);?>"><img data-src="<?php echo $main_image?>" src="<?php echo $site_url?>/images/loading.svg" alt="<?php echo $response->results[0]->trackName;?>"></a>

</div>
<h3><?php echo $response->results[0]->trackName;?></h3>
<h4><?php echo $byartist_mpage?> <?php echo $artist_title;?></h4>
<ul style="list-style:none;padding: 0px;">
<li><b><?php echo $release_mpage;?>:</b> <?php echo substr($response->results[0]->releaseDate,0,10);?></li>
<li><b><?php echo $cat_mpage;?>:</b> <?php echo $response->results[0]->primaryGenreName;?></li>
</ul>
<p>
<?php $feat_descr = strip_tags($response->results[0]->longDescription); ?>
<?php echo substr($feat_descr,0,530); ?>...
</p>
<a href="<?php echo $site_url;?>/movie/<?php echo $response->results[0]->trackId;?>/<?php echo cano($response->results[0]->trackName);?>" style="margin-right: 10px;" class="btn btn-raised btn-warning"><?php echo $rmore_title;?></a>
</div>
</div>
<!--end col-md-12 -->

<?php 
$data = file_get_contents('https://itunes.apple.com/lookup?id='.$feat_id6.'&media=movie&entity=movie&country='.$site_country.'');
$response = json_decode($data);

$artist_title = $response->results[0]->artistName;
$sslimage = preg_replace('/http/ms', "http", $response->results[0]->artworkUrl100);
$sslimage = preg_replace('/.mzstatic/ms', ".mzstatic", $sslimage);
$main_image = preg_replace('/100x100bb.jpg/ms', "250x250bb.jpg", $sslimage);
// remove year from title
$response->results[0]->trackName = preg_replace('@\(.*?\)@', '', $response->results[0]->trackName);
?>
<div class="col-md-12" style="padding: 0px;">
<div class="featbox box2">
<div class="featimage">
<a href="<?php echo $site_url;?>/movie/<?php echo $response->results[0]->trackId;?>/<?php echo cano($response->results[0]->trackName);?>"><img data-src="<?php echo $main_image?>" src="<?php echo $site_url?>/images/loading.svg" alt="<?php echo $response->results[0]->trackName;?>"></a>

</div>
<h3><?php echo $response->results[0]->trackName;?></h3>
<h4><?php echo $byartist_mpage?> <?php echo $artist_title;?></h4>
<ul style="list-style:none;padding: 0px;">
<li><b><?php echo $release_mpage;?>:</b> <?php echo substr($response->results[0]->releaseDate,0,10);?></li>
<li><b><?php echo $cat_mpage;?>:</b> <?php echo $response->results[0]->primaryGenreName;?></li>
</ul>
<p>
<?php $feat_descr = strip_tags($response->results[0]->longDescription); ?>
<?php echo substr($feat_descr,0,530); ?>...
</p>
<a href="<?php echo $site_url;?>/movie/<?php echo $response->results[0]->trackId;?>/<?php echo cano($response->results[0]->trackName);?>" style="margin-right: 10px;" class="btn btn-raised btn-warning"><?php echo $rmore_title;?></a>
</div>
</div>
<!--end col-md-12 -->

<?php 
$data = file_get_contents('https://itunes.apple.com/lookup?id='.$feat_id7.'&media=movie&entity=movie&country='.$site_country.'');
$response = json_decode($data);

$artist_title = $response->results[0]->artistName;
$sslimage = preg_replace('/http/ms', "http", $response->results[0]->artworkUrl100);
$sslimage = preg_replace('/.mzstatic/ms', ".mzstatic", $sslimage);
$main_image = preg_replace('/100x100bb.jpg/ms', "250x250bb.jpg", $sslimage);
// remove year from title
$response->results[0]->trackName = preg_replace('@\(.*?\)@', '', $response->results[0]->trackName);
?>
<div class="col-md-12" style="padding: 0px;">
<div class="featbox box2">
<div class="featimage">
<a href="<?php echo $site_url;?>/movie/<?php echo $response->results[0]->trackId;?>/<?php echo cano($response->results[0]->trackName);?>"><img data-src="<?php echo $main_image?>" src="<?php echo $site_url?>/images/loading.svg" alt="<?php echo $response->results[0]->trackName;?>"></a>

</div>
<h3><?php echo $response->results[0]->trackName;?></h3>
<h4><?php echo $byartist_mpage?> <?php echo $artist_title;?></h4>
<ul style="list-style:none;padding: 0px;">
<li><b><?php echo $release_mpage;?>:</b> <?php echo substr($response->results[0]->releaseDate,0,10);?></li>
<li><b><?php echo $cat_mpage;?>:</b> <?php echo $response->results[0]->primaryGenreName;?></li>
</ul>
<p>
<?php $feat_descr = strip_tags($response->results[0]->longDescription); ?>
<?php echo substr($feat_descr,0,530); ?>...
</p>
<a href="<?php echo $site_url;?>/movie/<?php echo $response->results[0]->trackId;?>/<?php echo cano($response->results[0]->trackName);?>" style="margin-right: 10px;" class="btn btn-raised btn-warning"><?php echo $rmore_title;?></a>
</div>
</div>
<!--end col-md-12 -->

<?php 
$data = file_get_contents('https://itunes.apple.com/lookup?id='.$feat_id8.'&media=movie&entity=movie&country='.$site_country.'');
$response = json_decode($data);

$artist_title = $response->results[0]->artistName;
$sslimage = preg_replace('/http/ms', "http", $response->results[0]->artworkUrl100);
$sslimage = preg_replace('/.mzstatic/ms', ".mzstatic", $sslimage);
$main_image = preg_replace('/100x100bb.jpg/ms', "250x250bb.jpg", $sslimage);
// remove year from title
$response->results[0]->trackName = preg_replace('@\(.*?\)@', '', $response->results[0]->trackName);
?>
<div class="col-md-12" style="padding: 0px;">
<div class="featbox box2">
<div class="featimage">
<a href="<?php echo $site_url;?>/movie/<?php echo $response->results[0]->trackId;?>/<?php echo cano($response->results[0]->trackName);?>"><img data-src="<?php echo $main_image?>" src="<?php echo $site_url?>/images/loading.svg" alt="<?php echo $response->results[0]->trackName;?>"></a>

</div>
<h3><?php echo $response->results[0]->trackName;?></h3>
<h4><?php echo $byartist_mpage?> <?php echo $artist_title;?></h4>
<ul style="list-style:none;padding: 0px;">
<li><b><?php echo $release_mpage;?>:</b> <?php echo substr($response->results[0]->releaseDate,0,10);?></li>
<li><b><?php echo $cat_mpage;?>:</b> <?php echo $response->results[0]->primaryGenreName;?></li>
</ul>
<p>
<?php $feat_descr = strip_tags($response->results[0]->longDescription); ?>
<?php echo substr($feat_descr,0,530); ?>...
</p>
<a href="<?php echo $site_url;?>/movie/<?php echo $response->results[0]->trackId;?>/<?php echo cano($response->results[0]->trackName);?>" style="margin-right: 10px;" class="btn btn-raised btn-warning"><?php echo $rmore_title;?></a>
</div>
</div>
<!--end col-md-12 -->

<?php 
$data = file_get_contents('https://itunes.apple.com/lookup?id='.$feat_id9.'&media=movie&entity=movie&country='.$site_country.'');
$response = json_decode($data);

$artist_title = $response->results[0]->artistName;
$sslimage = preg_replace('/http/ms', "http", $response->results[0]->artworkUrl100);
$sslimage = preg_replace('/.mzstatic/ms', ".mzstatic", $sslimage);
$main_image = preg_replace('/100x100bb.jpg/ms', "250x250bb.jpg", $sslimage);
// remove year from title
$response->results[0]->trackName = preg_replace('@\(.*?\)@', '', $response->results[0]->trackName);
?>
<div class="col-md-12" style="padding: 0px;">
<div class="featbox box2">
<div class="featimage">
<a href="<?php echo $site_url;?>/movie/<?php echo $response->results[0]->trackId;?>/<?php echo cano($response->results[0]->trackName);?>"><img data-src="<?php echo $main_image?>" src="<?php echo $site_url?>/images/loading.svg" alt="<?php echo $response->results[0]->trackName;?>"></a>

</div>
<h3><?php echo $response->results[0]->trackName;?></h3>
<h4><?php echo $byartist_mpage?> <?php echo $artist_title;?></h4>
<ul style="list-style:none;padding: 0px;">
<li><b><?php echo $release_mpage;?>:</b> <?php echo substr($response->results[0]->releaseDate,0,10);?></li>
<li><b><?php echo $cat_mpage;?>:</b> <?php echo $response->results[0]->primaryGenreName;?></li>
</ul>
<p>
<?php $feat_descr = strip_tags($response->results[0]->longDescription); ?>
<?php echo substr($feat_descr,0,530); ?>...
</p>
<a href="<?php echo $site_url;?>/movie/<?php echo $response->results[0]->trackId;?>/<?php echo cano($response->results[0]->trackName);?>" style="margin-right: 10px;" class="btn btn-raised btn-warning"><?php echo $rmore_title;?></a>
</div>
</div>
<!--end col-md-12 -->

<?php 
$data = file_get_contents('https://itunes.apple.com/lookup?id='.$feat_id10.'&media=movie&entity=movie&country='.$site_country.'');
$response = json_decode($data);

$artist_title = $response->results[0]->artistName;
$sslimage = preg_replace('/http/ms', "http", $response->results[0]->artworkUrl100);
$sslimage = preg_replace('/.mzstatic/ms', ".mzstatic", $sslimage);
$main_image = preg_replace('/100x100bb.jpg/ms', "250x250bb.jpg", $sslimage);
// remove year from title
$response->results[0]->trackName = preg_replace('@\(.*?\)@', '', $response->results[0]->trackName);
?>
<div class="col-md-12" style="padding: 0px;">
<div class="featbox box2">
<div class="featimage">
<a href="<?php echo $site_url;?>/movie/<?php echo $response->results[0]->trackId;?>/<?php echo cano($response->results[0]->trackName);?>"><img data-src="<?php echo $main_image?>" src="<?php echo $site_url?>/images/loading.svg" alt="<?php echo $response->results[0]->trackName;?>"></a>

</div>
<h3><?php echo $response->results[0]->trackName;?></h3>
<h4><?php echo $byartist_mpage?> <?php echo $artist_title;?></h4>
<ul style="list-style:none;padding: 0px;">
<li><b><?php echo $release_mpage;?>:</b> <?php echo substr($response->results[0]->releaseDate,0,10);?></li>
<li><b><?php echo $cat_mpage;?>:</b> <?php echo $response->results[0]->primaryGenreName;?></li>
</ul>
<p>
<?php $feat_descr = strip_tags($response->results[0]->longDescription); ?>
<?php echo substr($feat_descr,0,530); ?>...
</p>
<a href="<?php echo $site_url;?>/movie/<?php echo $response->results[0]->trackId;?>/<?php echo cano($response->results[0]->trackName);?>" style="margin-right: 10px;" class="btn btn-raised btn-warning"><?php echo $rmore_title;?></a>
</div>
</div>
<!--end col-md-12 -->

<?php 
$data = file_get_contents('https://itunes.apple.com/lookup?id='.$feat_id11.'&media=movie&entity=movie&country='.$site_country.'');
$response = json_decode($data);

$artist_title = $response->results[0]->artistName;
$sslimage = preg_replace('/http/ms', "http", $response->results[0]->artworkUrl100);
$sslimage = preg_replace('/.mzstatic/ms', ".mzstatic", $sslimage);
$main_image = preg_replace('/100x100bb.jpg/ms', "250x250bb.jpg", $sslimage);
// remove year from title
$response->results[0]->trackName = preg_replace('@\(.*?\)@', '', $response->results[0]->trackName);
?>
<div class="col-md-12" style="padding: 0px;">
<div class="featbox box2">
<div class="featimage">
<a href="<?php echo $site_url;?>/movie/<?php echo $response->results[0]->trackId;?>/<?php echo cano($response->results[0]->trackName);?>"><img data-src="<?php echo $main_image?>" src="<?php echo $site_url?>/images/loading.svg" alt="<?php echo $response->results[0]->trackName;?>"></a>

</div>
<h3><?php echo $response->results[0]->trackName;?></h3>
<h4><?php echo $byartist_mpage?> <?php echo $artist_title;?></h4>
<ul style="list-style:none;padding: 0px;">
<li><b><?php echo $release_mpage;?>:</b> <?php echo substr($response->results[0]->releaseDate,0,10);?></li>
<li><b><?php echo $cat_mpage;?>:</b> <?php echo $response->results[0]->primaryGenreName;?></li>
</ul>
<p>
<?php $feat_descr = strip_tags($response->results[0]->longDescription); ?>
<?php echo substr($feat_descr,0,530); ?>...
</p>
<a href="<?php echo $site_url;?>/movie/<?php echo $response->results[0]->trackId;?>/<?php echo cano($response->results[0]->trackName);?>" style="margin-right: 10px;" class="btn btn-raised btn-warning"><?php echo $rmore_title;?></a>
</div>
</div>
<!--end col-md-12 -->

<?php 
$data = file_get_contents('https://itunes.apple.com/lookup?id='.$feat_id12.'&media=movie&entity=movie&country='.$site_country.'');
$response = json_decode($data);

$artist_title = $response->results[0]->artistName;
$sslimage = preg_replace('/http/ms', "http", $response->results[0]->artworkUrl100);
$sslimage = preg_replace('/.mzstatic/ms', ".mzstatic", $sslimage);
$main_image = preg_replace('/100x100bb.jpg/ms', "250x250bb.jpg", $sslimage);
// remove year from title
$response->results[0]->trackName = preg_replace('@\(.*?\)@', '', $response->results[0]->trackName);
?>
<div class="col-md-12" style="padding: 0px;">
<div class="featbox box2">
<div class="featimage">
<a href="<?php echo $site_url;?>/movie/<?php echo $response->results[0]->trackId;?>/<?php echo cano($response->results[0]->trackName);?>"><img data-src="<?php echo $main_image?>" src="<?php echo $site_url?>/images/loading.svg" alt="<?php echo $response->results[0]->trackName;?>"></a>

</div>
<h3><?php echo $response->results[0]->trackName;?></h3>
<h4><?php echo $byartist_mpage?> <?php echo $artist_title;?></h4>
<ul style="list-style:none;padding: 0px;">
<li><b><?php echo $release_mpage;?>:</b> <?php echo substr($response->results[0]->releaseDate,0,10);?></li>
<li><b><?php echo $cat_mpage;?>:</b> <?php echo $response->results[0]->primaryGenreName;?></li>
</ul>
<p>
<?php $feat_descr = strip_tags($response->results[0]->longDescription); ?>
<?php echo substr($feat_descr,0,530); ?>...
</p>
<a href="<?php echo $site_url;?>/movie/<?php echo $response->results[0]->trackId;?>/<?php echo cano($response->results[0]->trackName);?>" style="margin-right: 10px;" class="btn btn-raised btn-warning"><?php echo $rmore_title;?></a>
</div>
</div>
<!--end col-md-12 -->

<div class="pagetitle">
<h1><?php echo $hometv_title;?></h1>
</div>
<div class="pageresults tv">
<input type="radio" name="viewswitch" class="viewswitch-small" checked="checked" />
<span class="control first"><i class="material-icons">apps</i></span>

<input type="radio" name="viewswitch" class="viewswitch-medium" />
<span class="control"><i class="material-icons">view_module</i></span>		
			
<input type="radio" name="viewswitch" class="viewswitch-large" />
<span class="control last"><i class="material-icons">menu</i></span>

<div class="genre-filter">
<li class="dropdown">
		<a href="#" data-target="#" class="dropdown-toggle" data-toggle="dropdown"><?php echo $filter_title;?> <b class="caret"></b></a>
		<ul class="dropdown-menu">
			<div class="drop-row">
			<li><a href="<?php echo $site_url;?>/top-tv-seasons"><?php echo $tvgtitle_all;?></a></li>		
			<li><a href="<?php echo $site_url;?>/top-tv-seasons/4003/<?php echo canogenre($tvgtitle_1);?>"><?php echo $tvgtitle_1;?></a></li>
			<li><a href="<?php echo $site_url;?>/top-tv-seasons/4002/<?php echo canogenre($tvgtitle_2);?>"><?php echo $tvgtitle_2;?></a></li>
			<li><a href="<?php echo $site_url;?>/top-tv-seasons/4004/<?php echo canogenre($tvgtitle_3);?>"><?php echo $tvgtitle_3;?></a></li>
			<li><a href="<?php echo $site_url;?>/top-tv-seasons/4000/<?php echo canogenre($tvgtitle_4);?>"><?php echo $tvgtitle_4;?></a></li>
			<li><a href="<?php echo $site_url;?>/top-tv-seasons/4001/<?php echo canogenre($tvgtitle_5);?>"><?php echo $tvgtitle_5;?></a></li>
			<li><a href="<?php echo $site_url;?>/top-tv-seasons/4005/<?php echo canogenre($tvgtitle_6);?>"><?php echo $tvgtitle_6;?></a></li>
			<li><a href="<?php echo $site_url;?>/top-tv-seasons/4006/<?php echo canogenre($tvgtitle_7);?>"><?php echo $tvgtitle_7;?></a></li>
			<li><a href="<?php echo $site_url;?>/top-tv-seasons/4007/<?php echo canogenre($tvgtitle_8);?>"><?php echo $tvgtitle_8;?></a></li>
			<li><a href="<?php echo $site_url;?>/top-tv-seasons/4008/<?php echo canogenre($tvgtitle_9);?>"><?php echo $tvgtitle_9;?></a></li>
			<li><a href="<?php echo $site_url;?>/top-tv-seasons/4009/<?php echo canogenre($tvgtitle_10);?>"><?php echo $tvgtitle_10;?></a></li>
			<li><a href="<?php echo $site_url;?>/top-tv-seasons/4010/<?php echo canogenre($tvgtitle_11);?>"><?php echo $tvgtitle_11;?></a></li>
			</div>
		</ul>
</li>
</div>

<ul class="page-itemlist">
<?php
// Use local store
$string = file_get_contents('https://itunes.apple.com/'.$site_country.'/rss/toptvseasons/limit=18/xml');
// Remove the colon ":" in the <xxx:yyy> to be <xxxyyy>
$string = preg_replace("/(<\/?)(\w+):([^>]*>)/", "$1$2$3", $string);
$xml = simplexml_load_string($string);
// US store fallback
if (empty($xml->entry->id)) {
$string = file_get_contents('https://itunes.apple.com/us/rss/toptvseasons/limit=18/xml');
// Remove the colon ":" in the <xxx:yyy> to be <xxxyyy>
$string = preg_replace("/(<\/?)(\w+):([^>]*>)/", "$1$2$3", $string);
$xml = simplexml_load_string($string);
}


// Output
$rssresults = '';

foreach ($xml->entry as $val) {
    // edit foreach
	$musicid = $val->id;
	$musicid = str_replace("/id/","xxx",$musicid);
	$musicid=explode('/id',$musicid);
	$musicid=explode('?',$musicid[1]);
	$catid = $val->category->attributes()->scheme;
	$catid = str_replace("/id/","xxx",$catid);
	$catid=explode('/id',$catid);
	$catid=explode('?',$catid[1]);
	$sslimage = preg_replace('/http/ms', "http", $val->imimage[2]);
	$sslimage = preg_replace('/.mzstatic/ms', ".mzstatic", $sslimage);
	$bigimage = preg_replace('/170x170/ms', "200x200", $sslimage);
	//$val->imname = preg_replace('@\(.*?\)@', '', $val->imname);
	
    $rssresults .= '<li class="page-item"><div class="pagethumb" data-toggle="tooltip" data-placement="top" title="'.$val->imname.'"><a href="'.$site_url.'/tv/'.$musicid[0].'/'.cano($val->imname).'"><img data-src="'.$bigimage.'" src="'.$site_url.'/images/loading.svg" ></a></div>
		<div class="info"><h3><a href="'.$site_url.'/tv/'.$musicid[0].'/'.cano($val->imname).'">'.$val->imname.'</a></h3>
		<h4>'.$val->imitemCount.' '.$nr_episodes.'</h4>
		<a class="genre" href="'.$site_url.'/top-tv-seasons/'.$catid[0].'/'.cano($val->category->attributes()->label).'">'.$val->category->attributes()->label.'</a>
		
		</div>
	</li>';
   
}
echo $rssresults;

?>
</ul>
<p>Sehen Sie sich Ihre Lieblings-Filme und Serien in ausgezeichneter Qualität großen Spaß und echten Spaß. Wir haben versucht, ein gemütliches, komfortables, verständliches und einfach zu bedienendes virtuelles Kino movie4k zu schaffen, in dem Sie Ihre Lieblingsfilme völlig kostenlos ansehen können, ohne die Passage der aufdringlichen Registrierung, sowie ohne Abonnementgebühr.</p>

<p>Filme im Internet sind sehr beliebt, jetzt muss man nicht mehr auf die Premiere im nächsten Kino warten. Dank der komfortablen und verständlichen Online-Plattform können Sie Soundeffekte anpassen, die Bildqualität einstellen und den Film sogar auf Ihr Gerät herunterladen. Man verbringt keinen Pfennig, um den Abend mit einer Tasse Kaffee und einem guten Film zu verbringen.</p>

<p>Das Kino bietet eine schicke Auswahl an Genres und Kategorien: Faszinierende und lustige Komödie; Erschreckende Thriller; Schrecken abkühlen; Schöne, sanfte romantische Filme; Kognitive Dokumentarfilme; Erstaunliche Musikfilme; Spannende Western-und Action; Abenteuerfilme; Animationsfilme für Kinder und Erwachsene; Dramen und Kämpfer; Familienfilme des in-und ausländischen Kinos; Beliebte Fernsehfilme, Modeserie; Kognitive Science-Fiction; Geheimnisvolle Detektive; Kriminelle und interessante historische</p> Filmmeistereien.

<p>In der Videothek stehen mehr als 10 000 000 Filme von ausgezeichneter Qualität mit exzellenter Duplikation zur Verfügung. Sie werden Ihr Lieblingsbild jederzeit sehen können. Wenn Sie weg müssen, machen Sie sich keine Sorgen, was Sie den interessantesten Moment verpassen. Klicken Sie dazu einfach auf die Pause.</p>

<p>Im Internet gibt es viele Portale, auf denen man Serien, Cartoons, Anime und Filme anschauen kann, aber nicht alle sind korrekt organisiert. Um den Film zu sehen, brachte außergewöhnlich gute Laune, Freude, ist es wichtig, die richtige Seite zu wählen.</p>

<p>Wenn Sie unser virtuelles Kino movie4k besuchen, finden Sie in wenigen Sekunden einen Film, den Sie sehen möchten. Es ist möglich dank einfacher und bequemer Navigation, verständliches System der Suche. Nutzer des Portals haben die Möglichkeit, Filme nach Jahren zu sortieren, Länder Hersteller. Mit einem speziellen Filter können Sie Serien und Filme in den folgenden Sprachen auswählen: Spanisch; Deutsch Englisch Französisch Italienisch.</p>

<p>Es ist wichtig zu beachten, dass alle Filme ausschließlich in höchster Qualität präsentiert werden, nämlich HD 720 und HD 1080, sowie mit professioneller Synchronisation. Der Inhalt der Website ist legal, alle Videos sind streng urheberrechtlich geschützt, sind rechtlicher Herkunft.</p>

<p>Merkmale und Vorteile des Kinosortes:</p>

    <p>Eine riesige Sammlung von Filmen unterschiedlicher Genres und Richtungen;</p>
    <p>Die besten Filme ausländischer, inländischer Hersteller;</p>
    <p>Professionelle Vervielfältigung;</p>
    <p>Qualität HD 720 und HD 1080;</p>
    <p>100% legale und kostenlose Betrachtung;</p>
    <p>Systematische Auffüllung der Kategorien durch Neuheiten;</p>
    <p>Bequemes, einfaches Navigieren;</p>
    <p>kompatibel mit allen Betriebssystemen und modernen Gadgets;</p>
    <p>Möglichkeit, Kommentare abzugeben.</p>

<p>Nutzer unseres Portals MOVIE4K schauen TV-Serien und Filme zu jeder Tageszeit ohne Einschränkungen an. Wir leben in einer Welt, in der jeden Tag etwas Neues und Ungewöhnliches passiert. Deshalb ist es sehr schwierig, alle Neuheiten und Blockbuster der Filmindustrie nachzuvollziehen. Um immer in der Lage zu sein, Filme in guter Qualität zu sehen, können Sie die Website Lesezeichen. Mit Hilfe unseres Portals kann jeder Nutzer Freunde, Kollegen, die sich mit ihrem Bewusstsein in der Welt der Filmproduktion auskennen, überraschen.</p>
</div>
<!-- end latestapps -->
<script src="<?php echo $site_url;?>/js/imglazyload.js"></script>
<script>
			//lazy loading
			$('.container img').imgLazyLoad({
				// jquery selector or JS object
				container: window,
				// jQuery animations: fadeIn, show, slideDown
				effect: 'fadeIn',
				// animation speed
				speed: 600,
				// animation delay
				delay: 400,
				// callback function
				callback: function(){}
			});
</script>
<script language="JavaScript" type="text/javascript" src="<?php echo $site_url;?>/js/bigstar-rating.js"></script>
<script type="text/javascript" language="JavaScript">
jQuery(function() {
           jQuery('span.bigstars').bigstars();
      });
</script>
<script>
$(document).ready(function(){

	// hide #back-top first
	$("#back-top").hide();
	
	// fade in #back-top
	$(function () {
		$(window).scroll(function () {
			if ($(this).scrollTop() > 200) {
				$('#back-top').fadeIn();
			} else {
				$('#back-top').fadeOut();
			}
		});

		// scroll body to 0px on click
		$('#back-top a').click(function () {
			$('body,html').animate({
				scrollTop: 0
			}, 800);
			return false;
		});
	});

});
</script>
<p id="back-top"><a href="#top"><i class="material-icons">keyboard_arrow_up</i></a></p>
</div><!-- end .container -->
</div><!-- end .homeframe -->
<?php include 'includes/footer.php'; ?>
</body>
</html>
<?php
######## Your Website Content Ends here #########

if (!is_dir($cache_folder)) { //create a new folder if we need to
    mkdir($cache_folder);
}
if(!$ignore){
    $fp = fopen($cache_file, 'w');  //open file for writing
    fwrite($fp, ob_get_contents()); //write contents of the output buffer in Cache file
    fclose($fp); //Close file pointer
}
ob_end_flush(); //Flush and turn off output buffering

?>
