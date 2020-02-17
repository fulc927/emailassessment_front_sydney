# emailassessment_front_sydney
queue_seb.php
-------------
function generateRandomString($length = 10) {
	$characters = '0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ';
	$charactersLength = strlen($characters);

header.php
----------
\<?php<br />
include_once 'queue_seb.php';<br />
setcookie( "userlogin", $bdkey ,time()+3600 );<br />
$_COOKIE['userlogin'] = $bdkey;<br />

inc/slider.php
--------------
 \<h2 class="maintitle">\<?php print_r($_COOKIE["userlogin"]); ?>\</h2>

httpdocs/wp-content/themes/sydney/scoring.php
---------------------------------------------

\<?php /* Template Name: scoring */ ?><br />
\<?php<br />
\/**<br />
 \* The template for displaying all pages.<br />
 \*<br />
 \* This is the template that displays all pages by default.<br />
 \* Please note that this is the WordPress construct of pages<br />
 \* and that other 'pages' on your WordPress site will use a<br />
 \* different template.<br />
 \*<br />
 \* @package Sydney<br />
 \*/<br />
\get_header(); ?><br />
\<p  onclick="work()"><br />
\<a href="#">Résultat\</a> \</p><br />
\<p id="result" class="result">\</p><br />

js/main.min.js  UNMINIFIED
--------------------------
$(function work() {<br />
						$('.mainnav a[href*="#"], a.roll-button[href*="#"], .smoothscroll[href*="#"], .smoothscroll a[href*="#"]').on('click',function (work)                {<br />
				$.ajax({<br />
				url:"consume.php",<br />
				data: {action: 'consume'},<br />
				type: "post", //request type<br />
				success:function(result){<br />
				//alert(result);<br />
				$('#result').html(result);<br />
				}<br />
				});<br />
				}<br />
				);<br />

				});


consume.php
-----------
 $exchange->getArgument($o);

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

amqpconnect.ini
---------------
servername=server_ip_or_dns<br />
username=<br />
password=<br />

