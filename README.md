# emailassessment_front_sydney
queue_seb.php
-------------
function generateRandomString($length = 10) {
	$characters = '0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ';
	$charactersLength = strlen($characters);

header.php
----------
<?php
//SEB
include_once 'queue_seb.php';
setcookie( "userlogin", $bdkey ,time()+3600 );
$_COOKIE['userlogin'] = $bdkey;
/**

inc/slider.php
--------------
 <h2 class="maintitle"><?php print_r($_COOKIE["userlogin"]); ?></h2>

js/main.min.js  UNMINIFIED
--------------------------
$(function work() {
						$('.mainnav a[href*="#"], a.roll-button[href*="#"], .smoothscroll[href*="#"], .smoothscroll a[href*="#"]').on('click',function (work)                {
				$.ajax({
				url:"consume.php",
				data: {action: 'consume'},
				type: "post", //request type
				success:function(result){
				//alert(result);
				$('#result').html(result);
				}
				});
				}
				);

				});


consume.php
-----------
 $exchange->getArgument($o);

		////////
				$callback_func = function(AMQPEnvelope $message, AMQPQueue $queue) use (&$max_jobs) {
				global $i;
				//echo json_encode($message->getBody()). "\n";
				echo "Message $i: " . $message->getBody() . "\n";
				$i++;
				if ($i = 1) {
				// Bail after 1 message
						$_COOKIE['userlogin'] = '';
						return false;
				}
				};


httpdocs/wp-content/themes/sydney/scoring.php
---------------------------------------------

<?php /* Template Name: scoring */ ?>
<?php
/**
 * The template for displaying all pages.
 *
 * This is the template that displays all pages by default.
 * Please note that this is the WordPress construct of pages
 * and that other 'pages' on your WordPress site will use a
 * different template.
 *
 * @package Sydney
 */

get_header(); ?>
<p> salut les loulous from template page </p>
 <p  onclick="work()">
<a href="#">Résultat</a> </p>
			<p id="result" class="result"></p>
