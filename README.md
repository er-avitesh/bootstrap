
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<link rel="profile" href="http://gmpg.org/xfn/11">

<title>Distributed Tracing with Spring Cloud &#8211; Spring Digest</title>

		<style type="text/css">
img.wp-smiley,
img.emoji {
	display: inline !important;
	border: none !important;
	box-shadow: none !important;
	height: 1em !important;
	width: 1em !important;
	margin: 0 .07em !important;
	vertical-align: -0.1em !important;
	background: none !important;
	padding: 0 !important;
}
</style>
	<link rel='stylesheet' id='all-css-0-1' href='https://s1.wp.com/_static/??-eJydU+1uwyAMfKEx1KrrtB/TngWIm7gxMQLSrG8/J+n6lY5p+xP5zJ1tLkYPQTnuMnRZ+14F6mvskh6CY6+SR4LjHXp2KT3px7LU2+QihowsaMdEPJT4DR8gKttbSyDqfCQ407Fz1FeSloSuTGpQCqRnj92Ssk86y3lr+fMclPoStqMKcjCuVRP6oS+mrC3xxLLRxONpyusxHjQwlRCUNfHk3RnPItQd5+k+56BUzXEEyftg8sjwUKEBAi+0ksyH7bdqDBu5a7HNPKq1IUJKSr4ee69yI41+Gc+Po8w+TrbdZErSGjqIsxEPw4V2nkaH3mrsKgggH2kkmDA1skzruzX6g3CcfPrX/2orezO3VpOPRaOxqiEnDb2ccougyAw6gw9k8uIhFAokdmhIza5dg7LnrOSWZnykN0DtyGAsSWVZ4Wq51WFdYkcQN2sJ68naCyyJMicVIXDMasfR3+OFdKx58YVjZSq5IrE1NHI//PvqZfO2WW3Xm9f9F8Hb2/0=?cssminify=yes' type='text/css' media='all' />
<style id='wpcom-admin-bar-inline-css' type='text/css'>

			.admin-bar {
				position: inherit !important;
				top: auto !important;
			}
			.admin-bar .goog-te-banner-frame {
				top: 32px !important
			}
			@media screen and (max-width: 782px) {
				.admin-bar .goog-te-banner-frame {
					top: 46px !important;
				}
			}
			@media screen and (max-width: 480px) {
				.admin-bar .goog-te-banner-frame {
					position: absolute;
				}
			}
		
</style>
<link rel='stylesheet' id='print-css-1-1' href='https://s2.wp.com/wp-content/mu-plugins/global-print/global-print.css?m=1465851035h&cssminify=yes' type='text/css' media='print' />
<link rel='stylesheet' id='all-css-2-1' href='https://s0.wp.com/_static/??-eJx9TssOwjAM+yFKgMG0C+Jbsq60QW0yNRn8PtsBEELs5Idsy/AYnRe2wAZlcmOeIrECDoXY9VihoFqoM3NyD7XSEPTjbb3qBv5MeCPhZeLN1uKjqLlrRqqgCStxfOFaS8UTZpclyrf4KVkKZb6ejhCz9JiXwKWc96em3XWHtuluTyr0Y1E=?cssminify=yes' type='text/css' media='all' />
<script type='text/javascript' src='https://s2.wp.com/_static/??-eJx9kFEKwjAMQC9kVycT9yOeZavZyGyb2qQbenr7MRFHFQIh5JHkRS9BoTc2XYH1lOOeID7WVE280/8A5XCMnUDl0L9hQ17Ai3ZJBZtG9Kw59WwiBkHK1UDW0rLF8+hALA6YuxEKXUc9WlCJIWbAS75qoAL3bYB+Rigt24iChM7cVATGJ5S8OXwUfz9spS7uXDft6dDWx2Y/vQBJS4U5'></script>
<link rel='stylesheet' id='all-css-0-2' href='https://s0.wp.com/wp-content/mu-plugins/highlander-comments/style.css?m=1530132353h&cssminify=yes' type='text/css' media='all' />
<!--[if lt IE 8]>
<link rel='stylesheet' id='highlander-comments-ie7-css'  href='https://s2.wp.com/wp-content/mu-plugins/highlander-comments/style-ie7.css?m=1351637563h&#038;ver=20110606' type='text/css' media='all' />
<![endif]-->
<link rel="EditURI" type="application/rsd+xml" title="RSD" href="https://aviteshdocs.wordpress.com/xmlrpc.php?rsd" />
<link rel="wlwmanifest" type="application/wlwmanifest+xml" href="https://s1.wp.com/wp-includes/wlwmanifest.xml" /> 
<link rel='prev' title='The Journey Begins' href='https://aviteshdocs.wordpress.com/2019/02/04/the-journey-begins/' />
<meta name="generator" content="WordPress.com" />
<link rel="canonical" href="https://aviteshdocs.wordpress.com/2019/02/04/distributed-tracing-with-spring-cloud/" />
<link rel='shortlink' href='https://wp.me/paGCzw-a' />
<link rel="alternate" type="application/json+oembed" href="https://public-api.wordpress.com/oembed/?format=json&amp;url=https%3A%2F%2Faviteshdocs.wordpress.com%2F2019%2F02%2F04%2Fdistributed-tracing-with-spring-cloud%2F&amp;for=wpcom-auto-discovery" /><link rel="alternate" type="application/xml+oembed" href="https://public-api.wordpress.com/oembed/?format=xml&amp;url=https%3A%2F%2Faviteshdocs.wordpress.com%2F2019%2F02%2F04%2Fdistributed-tracing-with-spring-cloud%2F&amp;for=wpcom-auto-discovery" />
<!-- Jetpack Open Graph Tags -->
<meta property="og:type" content="article" />
<meta property="og:title" content="Distributed Tracing with Spring Cloud" />
<meta property="og:url" content="https://aviteshdocs.wordpress.com/2019/02/04/distributed-tracing-with-spring-cloud/" />
<meta property="og:description" content="Context So, we have achieved the Microservice architecture pattern. Everything is well planned and designed. Requests often span multiple services. Each service handles a request by performing one …" />
<meta property="article:published_time" content="2019-02-04T20:31:51+00:00" />
<meta property="article:modified_time" content="2019-02-04T20:31:51+00:00" />
<meta property="og:site_name" content="Spring Digest" />
<meta property="og:image" content="https://aviteshdocs.files.wordpress.com/2019/02/dep.png" />
<meta property="og:image:width" content="995" />
<meta property="og:image:height" content="373" />
<meta property="og:locale" content="en_US" />
<meta name="twitter:site" content="@wordpressdotcom" />
<meta name="twitter:text:title" content="Distributed Tracing with Spring&nbsp;Cloud" />
<meta name="twitter:card" content="summary" />
<meta property="fb:app_id" content="249643311490" />
<meta property="article:publisher" content="https://www.facebook.com/WordPresscom" />

<!-- End Jetpack Open Graph Tags -->
<link rel="search" type="application/opensearchdescription+xml" href="https://aviteshdocs.wordpress.com/osd.xml" title="Spring Digest" />
<link rel="search" type="application/opensearchdescription+xml" href="https://s1.wp.com/opensearch.xml" title="WordPress.com" />
<link rel="pingback" href="https://aviteshdocs.wordpress.com/xmlrpc.php"><meta name="application-name" content="Spring Digest" /><meta name="msapplication-window" content="width=device-width;height=device-height" /><meta name="msapplication-tooltip" content="springBoot" /><meta name="msapplication-task" content="name=Edit post;action-uri=https://wordpress.com/post/aviteshdocs.wordpress.com/10;icon-uri=https://s2.wp.com/i/icons/post.ico" /><meta name="msapplication-task" content="name=Write a post;action-uri=https://wordpress.com/post/aviteshdocs.wordpress.com;icon-uri=https://s2.wp.com/i/icons/post.ico" /><meta name="msapplication-task" content="name=Moderate comments;action-uri=https://aviteshdocs.wordpress.com/wp-admin/edit-comments.php?comment_status=moderated;icon-uri=https://s2.wp.com/i/icons/comment.ico" /><meta name="msapplication-task" content="name=Upload new media;action-uri=https://aviteshdocs.wordpress.com/wp-admin/media-new.php;icon-uri=https://s2.wp.com/i/icons/media.ico" /><meta name="msapplication-task" content="name=Blog stats;action-uri=https://aviteshdocs.wordpress.com/wp-admin/index.php?page=stats;icon-uri=https://s1.wp.com/i/icons/stats.ico" /><meta name="description" content="Context So, we have achieved the Microservice architecture pattern. Everything is well planned and designed. Requests often span multiple services. Each service handles a request by performing one or more operations, e.g. database queries, publishes messages, etc. Everything is working fine. Everyone is happy and chilling, until. Problem: What we are going to do when&hellip;" />
<link rel="amphtml" href="https://aviteshdocs.wordpress.com/2019/02/04/distributed-tracing-with-spring-cloud/amp/"><style type="text/css" media="print">#wpadminbar { display:none; }</style>
	<style type="text/css" media="screen">
	html { margin-top: 32px !important; }
	* html body { margin-top: 32px !important; }
	@media screen and ( max-width: 782px ) {
		html { margin-top: 46px !important; }
		* html body { margin-top: 46px !important; }
	}
</style>
	<style type="text/css" id="syntaxhighlighteranchor"></style>
<link rel="icon" href="https://aviteshdocs.files.wordpress.com/2019/02/cropped-person-smartphone-office-table.jpeg?w=32" sizes="32x32" />
<link rel="icon" href="https://aviteshdocs.files.wordpress.com/2019/02/cropped-person-smartphone-office-table.jpeg?w=192" sizes="192x192" />
<link rel="apple-touch-icon-precomposed" href="https://aviteshdocs.files.wordpress.com/2019/02/cropped-person-smartphone-office-table.jpeg?w=180" />
<meta name="msapplication-TileImage" content="https://aviteshdocs.files.wordpress.com/2019/02/cropped-person-smartphone-office-table.jpeg?w=270" />
</head>

<body class="post-template-default single single-post postid-10 single-format-standard logged-in admin-bar no-customize-support wp-embed-responsive mp6 customizer-styles-applied highlander-enabled highlander-light">

<div id="page" class="hfeed site">
	<a class="skip-link screen-reader-text" href="#content">Skip to content</a>



	
	
	
	<div id="content-wrapper" class="content-wrapper">
		<div id="content" class="site-content">

	<div id="primary" class="content-area">
		<main id="main" class="site-main" role="main">

		
			
<article id="post-10" class="post-10 post type-post status-publish format-standard hentry category-uncategorized tag-distributed-tracing tag-microservices tag-pcf tag-spring-cloud">
			<header class="entry-header">
			<h1 class="entry-title">Distributed Tracing with Spring&nbsp;Cloud</h1>		</header><!-- .entry-header -->		<div class="entry-meta">
			<span class="byline">
				<a href="" title="Posts by itsAvitesh" rel="author">Avitesh Kesharwani</a>			</span>
							<span class="cat-links">
					<a href="" rel="category tag"></a>				</span><!-- .cat-links -->
			
			
			<span class="published-on">
				<time class="entry-date published updated" datetime="2019-02-04T20:31:51+00:00">February 4, 2019</time>			</span>

			</div><!-- .entry-meta -->
	
	<div class="entry-content">
		
<p style="font-size:24px;"><strong>Context</strong></p>



<p>So, we have achieved the Microservice architecture pattern. Everything is well planned and designed. Requests often span multiple services. Each service handles a request by performing one or more operations, e.g. database queries, publishes messages, etc.</p>



<div class="wp-block-image"><figure class="aligncenter"><img data-attachment-id="12" data-permalink="https://aviteshdocs.wordpress.com/qiohjwo/" data-orig-file="https://aviteshdocs.files.wordpress.com/2019/02/qiohjwo.png?w=1100" data-orig-size="507,463" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="qiohjwo" data-image-description="" data-medium-file="https://aviteshdocs.files.wordpress.com/2019/02/qiohjwo.png?w=1100?w=300" data-large-file="https://aviteshdocs.files.wordpress.com/2019/02/qiohjwo.png?w=1100?w=507" src="https://aviteshdocs.files.wordpress.com/2019/02/qiohjwo.png?w=1100" alt="" class="wp-image-12" srcset="https://aviteshdocs.files.wordpress.com/2019/02/qiohjwo.png 507w, https://aviteshdocs.files.wordpress.com/2019/02/qiohjwo.png?w=150 150w, https://aviteshdocs.files.wordpress.com/2019/02/qiohjwo.png?w=300 300w" sizes="(max-width: 507px) 100vw, 507px" /><figcaption> <br><strong> Everything is working fine. </strong></figcaption></figure></div>



<div class="wp-block-media-text alignwide has-media-on-the-right"><figure class="wp-block-media-text__media"><img data-attachment-id="14" data-permalink="https://aviteshdocs.wordpress.com/download/" data-orig-file="https://aviteshdocs.files.wordpress.com/2019/02/download.jpg?w=1100" data-orig-size="256,197" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="download" data-image-description="" data-medium-file="https://aviteshdocs.files.wordpress.com/2019/02/download.jpg?w=1100?w=256" data-large-file="https://aviteshdocs.files.wordpress.com/2019/02/download.jpg?w=1100?w=256" src="https://aviteshdocs.files.wordpress.com/2019/02/download.jpg?w=1100" alt="" class="wp-image-14" srcset="https://aviteshdocs.files.wordpress.com/2019/02/download.jpg 256w, https://aviteshdocs.files.wordpress.com/2019/02/download.jpg?w=150 150w" sizes="(max-width: 256px) 100vw, 256px" /></figure><div class="wp-block-media-text__content">
<p class="has-large-font-size"> Everyone is happy and chilling, until. </p>
</div></div>



<div class="wp-block-media-text alignwide" style="grid-template-columns:31% auto;"><figure class="wp-block-media-text__media"><img data-attachment-id="19" data-permalink="https://aviteshdocs.wordpress.com/probl/" data-orig-file="https://aviteshdocs.files.wordpress.com/2019/02/probl.jpg?w=1100" data-orig-size="221,228" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="probl" data-image-description="" data-medium-file="https://aviteshdocs.files.wordpress.com/2019/02/probl.jpg?w=1100?w=221" data-large-file="https://aviteshdocs.files.wordpress.com/2019/02/probl.jpg?w=1100?w=221" src="https://aviteshdocs.files.wordpress.com/2019/02/probl.jpg?w=1100" alt="" class="wp-image-19" srcset="https://aviteshdocs.files.wordpress.com/2019/02/probl.jpg 221w, https://aviteshdocs.files.wordpress.com/2019/02/probl.jpg?w=145 145w" sizes="(max-width: 221px) 100vw, 221px" /></figure><div class="wp-block-media-text__content">
<p class="has-medium-font-size"><strong> Problem: </strong>What we are going to do when failure or delay occurs in any of the service in cluster. How we are going to identify which one of the services out of tons of services is causing slowness. How we are going to troubleshoot. That’s right, Microservice architecture gets us fast, responsive and scalability architecture but there are trade offs too. </p>
</div></div>



<div class="wp-block-media-text alignwide has-media-on-the-right"><figure class="wp-block-media-text__media"><img data-attachment-id="16" data-permalink="https://aviteshdocs.wordpress.com/mario/" data-orig-file="https://aviteshdocs.files.wordpress.com/2019/02/mario.jpg?w=1100" data-orig-size="468,578" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="mario" data-image-description="" data-medium-file="https://aviteshdocs.files.wordpress.com/2019/02/mario.jpg?w=1100?w=243" data-large-file="https://aviteshdocs.files.wordpress.com/2019/02/mario.jpg?w=1100?w=468" src="https://aviteshdocs.files.wordpress.com/2019/02/mario.jpg?w=1100" alt="" class="wp-image-16" srcset="https://aviteshdocs.files.wordpress.com/2019/02/mario.jpg 468w, https://aviteshdocs.files.wordpress.com/2019/02/mario.jpg?w=121 121w, https://aviteshdocs.files.wordpress.com/2019/02/mario.jpg?w=243 243w" sizes="(max-width: 468px) 100vw, 468px" /></figure><div class="wp-block-media-text__content">
<p class="has-medium-font-size"><strong>Brainstorming : </strong>We start thinking about options available like better logging and external monitoring tools. However External monitoring only tells you the overall response time and number of invocations, not much insight into the individual operations. And Log entries for a request are scattered across numerous logs</p>
</div></div>



<div class="wp-block-media-text alignwide" style="grid-template-columns:20% auto;"><figure class="wp-block-media-text__media"><img data-attachment-id="21" data-permalink="https://aviteshdocs.wordpress.com/attention/" data-orig-file="https://aviteshdocs.files.wordpress.com/2019/02/attention.png?w=1100" data-orig-size="500,567" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="attention" data-image-description="" data-medium-file="https://aviteshdocs.files.wordpress.com/2019/02/attention.png?w=1100?w=265" data-large-file="https://aviteshdocs.files.wordpress.com/2019/02/attention.png?w=1100?w=500" src="https://aviteshdocs.files.wordpress.com/2019/02/attention.png?w=1100" alt="" class="wp-image-21" srcset="https://aviteshdocs.files.wordpress.com/2019/02/attention.png 500w, https://aviteshdocs.files.wordpress.com/2019/02/attention.png?w=132 132w, https://aviteshdocs.files.wordpress.com/2019/02/attention.png?w=265 265w" sizes="(max-width: 500px) 100vw, 500px" /></figure><div class="wp-block-media-text__content">
<p><strong>NOTE :</strong> I will be using a set of Services for demo purpose here. Use case i am going to use is School clearance system for student. Where We have Student Clearance system which calls Finance Service and Libraray Service to check if there is any dues from that department. Finance service further calls FeeService and Transport service to check the same and respond accordingly.  They are just boiler plate apps calling each other

</p>
</div></div>



<div class="wp-block-media-text alignwide" style="grid-template-columns:82% auto;"><figure class="wp-block-media-text__media"><img data-attachment-id="25" data-permalink="https://aviteshdocs.wordpress.com/service-1/" data-orig-file="https://aviteshdocs.files.wordpress.com/2019/02/service-1.png?w=1100" data-orig-size="1699,519" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="service-1" data-image-description="" data-medium-file="https://aviteshdocs.files.wordpress.com/2019/02/service-1.png?w=1100?w=300" data-large-file="https://aviteshdocs.files.wordpress.com/2019/02/service-1.png?w=1100?w=1024" src="https://aviteshdocs.files.wordpress.com/2019/02/service-1.png?w=1100" alt="" class="wp-image-25" srcset="https://aviteshdocs.files.wordpress.com/2019/02/service-1.png?w=1100 1100w, https://aviteshdocs.files.wordpress.com/2019/02/service-1.png?w=150 150w, https://aviteshdocs.files.wordpress.com/2019/02/service-1.png?w=300 300w, https://aviteshdocs.files.wordpress.com/2019/02/service-1.png?w=768 768w, https://aviteshdocs.files.wordpress.com/2019/02/service-1.png?w=1024 1024w, https://aviteshdocs.files.wordpress.com/2019/02/service-1.png 1699w" sizes="(max-width: 1100px) 100vw, 1100px" /></figure><div class="wp-block-media-text__content">
<p style="text-align:center;">We
think our service architecture is like this.</p>
</div></div>



<div class="wp-block-media-text alignwide has-media-on-the-right" style="grid-template-columns:auto 83%;"><figure class="wp-block-media-text__media"><img data-attachment-id="27" data-permalink="https://aviteshdocs.wordpress.com/scalabale-1/" data-orig-file="https://aviteshdocs.files.wordpress.com/2019/02/scalabale-1.png?w=1100" data-orig-size="1689,770" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="scalabale-1" data-image-description="" data-medium-file="https://aviteshdocs.files.wordpress.com/2019/02/scalabale-1.png?w=1100?w=300" data-large-file="https://aviteshdocs.files.wordpress.com/2019/02/scalabale-1.png?w=1100?w=1024" src="https://aviteshdocs.files.wordpress.com/2019/02/scalabale-1.png?w=1100" alt="" class="wp-image-27" srcset="https://aviteshdocs.files.wordpress.com/2019/02/scalabale-1.png?w=1100 1100w, https://aviteshdocs.files.wordpress.com/2019/02/scalabale-1.png?w=150 150w, https://aviteshdocs.files.wordpress.com/2019/02/scalabale-1.png?w=300 300w, https://aviteshdocs.files.wordpress.com/2019/02/scalabale-1.png?w=768 768w, https://aviteshdocs.files.wordpress.com/2019/02/scalabale-1.png?w=1024 1024w, https://aviteshdocs.files.wordpress.com/2019/02/scalabale-1.png 1689w" sizes="(max-width: 1100px) 100vw, 1100px" /></figure><div class="wp-block-media-text__content">
<p style="text-align:center;"><strong>But Actually it’s like this in scalable infrastructure.</strong> Every service is having multiple instances, deployed in distributed environment , may be in different availability zones too.</p>
</div></div>



<div class="wp-block-media-text alignwide" style="grid-template-columns:23% auto;"><figure class="wp-block-media-text__media"><img data-attachment-id="32" data-permalink="https://aviteshdocs.wordpress.com/question_man_thinking_standing_activity_person_doubt-512/" data-orig-file="https://aviteshdocs.files.wordpress.com/2019/02/question_man_thinking_standing_activity_person_doubt-512.png?w=1100" data-orig-size="512,512" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="question_man_thinking_standing_activity_person_doubt-512" data-image-description="" data-medium-file="https://aviteshdocs.files.wordpress.com/2019/02/question_man_thinking_standing_activity_person_doubt-512.png?w=1100?w=300" data-large-file="https://aviteshdocs.files.wordpress.com/2019/02/question_man_thinking_standing_activity_person_doubt-512.png?w=1100?w=512" src="https://aviteshdocs.files.wordpress.com/2019/02/question_man_thinking_standing_activity_person_doubt-512.png?w=1100" alt="" class="wp-image-32" srcset="https://aviteshdocs.files.wordpress.com/2019/02/question_man_thinking_standing_activity_person_doubt-512.png 512w, https://aviteshdocs.files.wordpress.com/2019/02/question_man_thinking_standing_activity_person_doubt-512.png?w=150 150w, https://aviteshdocs.files.wordpress.com/2019/02/question_man_thinking_standing_activity_person_doubt-512.png?w=300 300w" sizes="(max-width: 512px) 100vw, 512px" /></figure><div class="wp-block-media-text__content">
<p style="text-align:center;" class="has-medium-font-size">In Architecture like that, its sometime impossible to troubleshoot and find where the slowness is.</p>



<p style="text-align:center;" class="has-medium-font-size">Surely,
you don’t want to tail the logs in all servers and instances and grep.</p>



<p style="text-align:center;" class="has-medium-font-size"><strong>So, what should we do ?????</strong></p>
</div></div>



<h2><strong><em>Solution:</em> Distributed Tracing.</strong></h2>



<div class="wp-block-media-text alignwide has-media-on-the-right" style="grid-template-columns:auto 18%;"><figure class="wp-block-media-text__media"><img data-attachment-id="35" data-permalink="https://aviteshdocs.wordpress.com/sol/" data-orig-file="https://aviteshdocs.files.wordpress.com/2019/02/sol.png?w=1100" data-orig-size="225,225" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="sol" data-image-description="" data-medium-file="https://aviteshdocs.files.wordpress.com/2019/02/sol.png?w=1100?w=225" data-large-file="https://aviteshdocs.files.wordpress.com/2019/02/sol.png?w=1100?w=225" src="https://aviteshdocs.files.wordpress.com/2019/02/sol.png?w=1100" alt="" class="wp-image-35" srcset="https://aviteshdocs.files.wordpress.com/2019/02/sol.png 225w, https://aviteshdocs.files.wordpress.com/2019/02/sol.png?w=150 150w" sizes="(max-width: 225px) 100vw, 225px" /></figure><div class="wp-block-media-text__content">
<ul><li>Distributed tracing, in general, is latency measurement of each component in a distributed transaction where multiple microservices are invoked to serve a single business use case. </li></ul>



<ul><li>Distributed tracing involves instrumentation of services for tracing. It means assigning unique request id to each external request coming in and passing the same to all the services which are processing that request. It also involves recording information like latency, start time and end time, error and exception. </li></ul>
</div></div>



<p style="font-size:18px;"><strong> Few things to know before we dive in Distributed Tracing. </strong></p>



<div class="wp-block-media-text alignwide" style="grid-template-columns:9% auto;"><figure class="wp-block-media-text__media"><img data-attachment-id="36" data-permalink="https://aviteshdocs.wordpress.com/7149-200/" data-orig-file="https://aviteshdocs.files.wordpress.com/2019/02/7149-200.png?w=1100" data-orig-size="200,200" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="7149-200" data-image-description="" data-medium-file="https://aviteshdocs.files.wordpress.com/2019/02/7149-200.png?w=1100?w=200" data-large-file="https://aviteshdocs.files.wordpress.com/2019/02/7149-200.png?w=1100?w=200" src="https://aviteshdocs.files.wordpress.com/2019/02/7149-200.png?w=1100" alt="" class="wp-image-36" srcset="https://aviteshdocs.files.wordpress.com/2019/02/7149-200.png 200w, https://aviteshdocs.files.wordpress.com/2019/02/7149-200.png?w=150 150w" sizes="(max-width: 200px) 100vw, 200px" /></figure><div class="wp-block-media-text__content">
<ul><li> <strong>Span</strong>: Spans are the basic unit of work. They keep track of the timing information. Can be created by annotation. All spans have unique ids. Spans share the trace id.</li><li> <strong>Trace: </strong>A set of spans forming a tree-like structure. The initial span that starts a trace is called a root span. The value of span id of that span is equal to trace id. </li><li> <strong>Baggage: </strong>These are the key value pair which got propagated between network boundaries. It Works for Http and Messaging based communication both.   </li></ul>
</div></div>



<div class="wp-block-media-text alignwide has-media-on-the-right" style="grid-template-columns:auto 24%;"><figure class="wp-block-media-text__media"><img data-attachment-id="37" data-permalink="https://aviteshdocs.wordpress.com/spring-by-pivotal-9066b55828deb3c10e27e609af322c40/" data-orig-file="https://aviteshdocs.files.wordpress.com/2019/02/spring-by-pivotal-9066b55828deb3c10e27e609af322c40.png?w=1100" data-orig-size="800,260" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="spring-by-pivotal-9066b55828deb3c10e27e609af322c40" data-image-description="" data-medium-file="https://aviteshdocs.files.wordpress.com/2019/02/spring-by-pivotal-9066b55828deb3c10e27e609af322c40.png?w=1100?w=300" data-large-file="https://aviteshdocs.files.wordpress.com/2019/02/spring-by-pivotal-9066b55828deb3c10e27e609af322c40.png?w=1100?w=800" src="https://aviteshdocs.files.wordpress.com/2019/02/spring-by-pivotal-9066b55828deb3c10e27e609af322c40.png?w=1100" alt="" class="wp-image-37" srcset="https://aviteshdocs.files.wordpress.com/2019/02/spring-by-pivotal-9066b55828deb3c10e27e609af322c40.png 800w, https://aviteshdocs.files.wordpress.com/2019/02/spring-by-pivotal-9066b55828deb3c10e27e609af322c40.png?w=150 150w, https://aviteshdocs.files.wordpress.com/2019/02/spring-by-pivotal-9066b55828deb3c10e27e609af322c40.png?w=300 300w, https://aviteshdocs.files.wordpress.com/2019/02/spring-by-pivotal-9066b55828deb3c10e27e609af322c40.png?w=768 768w" sizes="(max-width: 800px) 100vw, 800px" /></figure><div class="wp-block-media-text__content">
<p class="has-medium-font-size"><strong>Spring Cloud</strong> gives Sleuth , one of the project for distributed tracing.</p>
</div></div>



<h2> What is Sleuth? </h2>



<ul><li>Spring Cloud Sleuth is a distributed tracing tool for Spring Cloud. It borrows from <a href="http://research.google.com/pubs/pub36356.html">Dapper</a>, <a href="https://github.com/openzipkin/zipkin">Zipkin</a>, and <a href="http://htrace.incubator.apache.org/">HTrace</a>.</li><li>First release 2016-05-10</li><li>Used to generate the trace id, span id and add these information to the service calls in the headers and MDC, so that It can be used by tools like Zipkin and <a href="https://howtodoinjava.com/microservices/elk-stack-tutorial-example/">ELK</a> etc.</li><li>As it is from spring cloud family, once added to the CLASSPATH, it automatically integrated to the common communication channels like RestTemplate, Netflix Zuul, Spring MVC Controller and Messaging services.</li><li>Can propagate context (also known as baggage) between processes.</li><li>Sends spans to Zipkin via Http or Messaging.</li><li> Create or continue spans and add tags and logs through annotations.</li></ul>



<h2>








How Sleuth Works?



</h2>



<pre class="wp-block-preformatted"><strong>Add a dependency</strong> <br>To start Sleuth instrumentation, it’s enough to add a dependency to your project.<br>   &nbsp; ● spring-cloud-starter-sleuth <br><br><strong>Setup Sleuth</strong> <br>You can provide additional configuration options to adjust sampling, configure propagation, etc.<br> &nbsp; ● Sampling probability<br> &nbsp; ● Baggage and propagation keys <br><br><strong>Observe</strong><br>Sleuth adds tracing context propagation, log correlation and span sending to Zipkin compatible servers.<br> &nbsp; ● spring-cloud-starter-sleuth for log correlation only<br> &nbsp; ● spring-cloud-starter-zipkin for Zipkin </pre>



<h4><strong>Sleuth Traces from our demo service</strong></h4>



<p><strong>LOG
example =&gt; </strong>Below
is one log snippet after only adding sleuth in our build file.</p>



<pre class="wp-block-preformatted">2019-02-03T00:19:41.756-06:00 [APP/PROC/WEB/0] [OUT] 2019-02-03 06:19:41.755 INFO <strong>[studentClearance,333f2a32451cc559,333f2a32451cc559,true] </strong>34 --- [nio-8080-exec-9] l.s.controller.ClearanceContoller : Checking Student account for Clearance </pre>



<p style="font-size:14px;">If we notice in above log this particular section.<br><strong><em>[studentClearance,333f2a32451cc559,333f2a32451cc559,true] </em></strong>appended by sleuth.<strong><em><br></em></strong> So it contains [app_name,traceId,spanId,exportable]<br> Note first trace use to have same trace and span id. Exportable means weather this trace is exportable to Zipkin or kibana.</p>



<figure class="wp-block-image alignwide"><img data-attachment-id="42" data-permalink="https://aviteshdocs.wordpress.com/trace-1/" data-orig-file="https://aviteshdocs.files.wordpress.com/2019/02/trace-1.png?w=1100" data-orig-size="1594,962" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="trace-1" data-image-description="" data-medium-file="https://aviteshdocs.files.wordpress.com/2019/02/trace-1.png?w=1100?w=300" data-large-file="https://aviteshdocs.files.wordpress.com/2019/02/trace-1.png?w=1100?w=1024" src="https://aviteshdocs.files.wordpress.com/2019/02/trace-1.png?w=1100" alt="Trace Diagram of services" class="wp-image-42" srcset="https://aviteshdocs.files.wordpress.com/2019/02/trace-1.png?w=1100 1100w, https://aviteshdocs.files.wordpress.com/2019/02/trace-1.png?w=150 150w, https://aviteshdocs.files.wordpress.com/2019/02/trace-1.png?w=300 300w, https://aviteshdocs.files.wordpress.com/2019/02/trace-1.png?w=768 768w, https://aviteshdocs.files.wordpress.com/2019/02/trace-1.png?w=1024 1024w, https://aviteshdocs.files.wordpress.com/2019/02/trace-1.png 1594w" sizes="(max-width: 1100px) 100vw, 1100px" /><figcaption><strong>TRACE diagram for our Demo Services.</strong></figcaption></figure>



<h2>Lets take a pause and understand whats happening above.</h2>



<div class="wp-block-media-text alignwide" style="grid-template-columns:16% auto;"><figure class="wp-block-media-text__media"><img data-attachment-id="44" data-permalink="https://aviteshdocs.wordpress.com/thinking-1/" data-orig-file="https://aviteshdocs.files.wordpress.com/2019/02/thinking-1.jpg?w=1100" data-orig-size="826,992" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;1&quot;}" data-image-title="thinking-1" data-image-description="" data-medium-file="https://aviteshdocs.files.wordpress.com/2019/02/thinking-1.jpg?w=1100?w=250" data-large-file="https://aviteshdocs.files.wordpress.com/2019/02/thinking-1.jpg?w=1100?w=826" src="https://aviteshdocs.files.wordpress.com/2019/02/thinking-1.jpg?w=1100" alt="" class="wp-image-44" srcset="https://aviteshdocs.files.wordpress.com/2019/02/thinking-1.jpg 826w, https://aviteshdocs.files.wordpress.com/2019/02/thinking-1.jpg?w=125 125w, https://aviteshdocs.files.wordpress.com/2019/02/thinking-1.jpg?w=250 250w, https://aviteshdocs.files.wordpress.com/2019/02/thinking-1.jpg?w=768 768w" sizes="(max-width: 826px) 100vw, 826px" /></figure><div class="wp-block-media-text__content">
<p>

Above is trace diagram for one request from end to end. When Request initiated from Student Clearance service that created a trace X and span A, student clearance service called Library Clearance and Finance Clearance, which created their own span and so on.. Point to notice here is in complete request lifecycle , trace is same however spans are getting generated for each different calls, which gets generated automatically without any single line of code as there was RestTemplate calls happening to invoke other services.

</p>
</div></div>



<h3><strong>Custom tracing with Sleuth</strong></h3>



<p>As it is from spring cloud family, once added to the CLASSPATH, it automatically integrated to the common communication channels like RestTemplate, Netflix Zuul, Spring MVC Controller and Messaging services.<br>However what if that&#8217;s not enough and we want to trace for any particular block of code like method or class in service for latency. To do this we can also add custom tracing by adding spans wherever we want using single annotation.</p>



<pre class="wp-block-preformatted">@NewSpan(&lt;spanName&gt;)<br> public String someMethod(@SpanTag(&lt;anyTagName&gt;) String tag) {<br>      try {<br>           // LOGIC<br>      } catch (Exception e) {<br>          // LOGIC<br>      }<br> }</pre>



<figure class="wp-block-pullquote"><blockquote><p><strong> Since Spring Boot 2.0.0 Sleuth uses Brave </strong><a href="https://github.com/openzipkin/brave"><strong>https://github.com/openzipkin/brave</strong></a><strong> as the tracer implementation. </strong></p></blockquote></figure>



<h2>








What
is Brave?



</h2>



<ul><li>Brave is a library used to capture latency information about distributed operations.</li><li>First release 2013-04-28.</li><li>Comes with a dependency-free Tracer library.</li><li>Contains various instrumentations for libraries and connection types (e.g. JDBC, Servlet, Spring).</li><li>Integrates with logging tools such as SLF4J.</li><li>It reports tracing data to Zipkin as spans.</li><li>For legacy applications, contains Spring XML Configuration support, that allows you to setup tracing without any custom code.</li><li>Brave takes care of passing tracing information between threads / libraries / contexts for Hystrix, RxJava, Reactor, Rest Template, Feign, Messaging with Spring Integration, Zuul.</li></ul>



<h2><strong>How Brave embraced Sleuth?</strong></h2>



<ul><li>Tracing with Brave required less coding.</li><li>Brave had larger community which helps Sleuth to grow.</li><li>Added Client and server interceptors for grpc.</li><li>Added MySQL, MySQL v6 and MySQL v8 statement interceptor.</li><li>AWS XRay integration (AWS Distributed Tracing).</li><li>Added Decorators for Kafka 0.11+ and Kafka Streams 2.0+ clients.</li></ul>



<figure class="wp-block-image alignwide"><img data-attachment-id="47" data-permalink="https://aviteshdocs.wordpress.com/loc/" data-orig-file="https://aviteshdocs.files.wordpress.com/2019/02/loc.png?w=1100" data-orig-size="1286,599" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="loc" data-image-description="" data-medium-file="https://aviteshdocs.files.wordpress.com/2019/02/loc.png?w=1100?w=300" data-large-file="https://aviteshdocs.files.wordpress.com/2019/02/loc.png?w=1100?w=1024" src="https://aviteshdocs.files.wordpress.com/2019/02/loc.png?w=1100" alt="" class="wp-image-47" srcset="https://aviteshdocs.files.wordpress.com/2019/02/loc.png?w=1100 1100w, https://aviteshdocs.files.wordpress.com/2019/02/loc.png?w=150 150w, https://aviteshdocs.files.wordpress.com/2019/02/loc.png?w=300 300w, https://aviteshdocs.files.wordpress.com/2019/02/loc.png?w=768 768w, https://aviteshdocs.files.wordpress.com/2019/02/loc.png?w=1024 1024w, https://aviteshdocs.files.wordpress.com/2019/02/loc.png 1286w" sizes="(max-width: 1100px) 100vw, 1100px" /><figcaption>SOURCE : From SpringOne Platform</figcaption></figure>



<blockquote class="wp-block-quote"><p>Sleuth Developer were able to get rid of 10000 lined of code from Sleuth after implementing BRAVE in it, Reason behind that is , they really wanted to leverage the BRAVE interfaces and methods.</p></blockquote>



<div class="wp-block-media-text alignwide" style="grid-template-columns:34% auto;"><figure class="wp-block-media-text__media"><img data-attachment-id="50" data-permalink="https://aviteshdocs.wordpress.com/context-1/" data-orig-file="https://aviteshdocs.files.wordpress.com/2019/02/context-1.jpg?w=1100" data-orig-size="840,513" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="context-1" data-image-description="" data-medium-file="https://aviteshdocs.files.wordpress.com/2019/02/context-1.jpg?w=1100?w=300" data-large-file="https://aviteshdocs.files.wordpress.com/2019/02/context-1.jpg?w=1100?w=840" src="https://aviteshdocs.files.wordpress.com/2019/02/context-1.jpg?w=1100" alt="" class="wp-image-50" srcset="https://aviteshdocs.files.wordpress.com/2019/02/context-1.jpg 840w, https://aviteshdocs.files.wordpress.com/2019/02/context-1.jpg?w=150 150w, https://aviteshdocs.files.wordpress.com/2019/02/context-1.jpg?w=300 300w, https://aviteshdocs.files.wordpress.com/2019/02/context-1.jpg?w=768 768w" sizes="(max-width: 840px) 100vw, 840px" /></figure><div class="wp-block-media-text__content">
<h3 id="mce_155">PERFECT, we are able to trace the calls between services and also trace the errors/exception if happened.</h3>
</div></div>



<h2><strong>BUT&#8230;.What if one of the service is slow ?</strong></h2>



<figure class="wp-block-image alignwide"><img data-attachment-id="52" data-permalink="https://aviteshdocs.wordpress.com/scalabale-2/" data-orig-file="https://aviteshdocs.files.wordpress.com/2019/02/scalabale-2.png?w=1100" data-orig-size="1689,770" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="scalabale-2" data-image-description="" data-medium-file="https://aviteshdocs.files.wordpress.com/2019/02/scalabale-2.png?w=1100?w=300" data-large-file="https://aviteshdocs.files.wordpress.com/2019/02/scalabale-2.png?w=1100?w=1024" src="https://aviteshdocs.files.wordpress.com/2019/02/scalabale-2.png?w=1100" alt="" class="wp-image-52" srcset="https://aviteshdocs.files.wordpress.com/2019/02/scalabale-2.png?w=1100 1100w, https://aviteshdocs.files.wordpress.com/2019/02/scalabale-2.png?w=150 150w, https://aviteshdocs.files.wordpress.com/2019/02/scalabale-2.png?w=300 300w, https://aviteshdocs.files.wordpress.com/2019/02/scalabale-2.png?w=768 768w, https://aviteshdocs.files.wordpress.com/2019/02/scalabale-2.png?w=1024 1024w, https://aviteshdocs.files.wordpress.com/2019/02/scalabale-2.png 1689w" sizes="(max-width: 1100px) 100vw, 1100px" /></figure>



<h2 style="text-align:center;">Which one is slow?</h2>



<h2 style="text-align:center;"><br> How to find that in distributed system like this or more complex system ?</h2>



<div class="wp-block-media-text alignwide" style="grid-template-columns:20% auto;"><figure class="wp-block-media-text__media"><img data-attachment-id="53" data-permalink="https://aviteshdocs.wordpress.com/zipkin-logo-200x119/" data-orig-file="https://aviteshdocs.files.wordpress.com/2019/02/zipkin-logo-200x119.jpg?w=1100" data-orig-size="200,119" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;1&quot;}" data-image-title="zipkin-logo-200&#215;119" data-image-description="" data-medium-file="https://aviteshdocs.files.wordpress.com/2019/02/zipkin-logo-200x119.jpg?w=1100?w=200" data-large-file="https://aviteshdocs.files.wordpress.com/2019/02/zipkin-logo-200x119.jpg?w=1100?w=200" src="https://aviteshdocs.files.wordpress.com/2019/02/zipkin-logo-200x119.jpg?w=1100" alt="" class="wp-image-53" srcset="https://aviteshdocs.files.wordpress.com/2019/02/zipkin-logo-200x119.jpg 200w, https://aviteshdocs.files.wordpress.com/2019/02/zipkin-logo-200x119.jpg?w=150 150w" sizes="(max-width: 200px) 100vw, 200px" /></figure><div class="wp-block-media-text__content">
<p style="text-align:right;" class="has-large-font-size">Solution is <strong>ZIPKIN</strong></p>
</div></div>



<h2>








What
is <strong>Zipkin</strong>?



</h2>



<ul><li>Zipkin is a distributed tracing system.</li><li>It helps gather timing data needed to troubleshoot latency problems in microservice architectures.</li><li>Zipkin’s design is based on the Google Dapper paper.</li><li>It manages both the collection and lookup of this data. </li><li>This project includes a dependency-free library and a spring-boot server.</li><li>Storage options include in-memory, JDBC (mysql), Cassandra, and Elasticsearch.</li><li>Quickest way to start is to download zipkin jar from <a href="https://search.maven.org/remote_content?g=io.zipkin.java&amp;a=zipkin-server&amp;v=LATEST&amp;c=exec">https://search.maven.org/remote_content?g=io.zipkin.java&amp;a=zipkin-server&amp;v=LATEST&amp;c=exec</a> and run as executable jar. Once the server is running you can traces with zipkin UI..</li></ul>



<h2><strong>How Zipkin works with Sleuth?</strong></h2>



<pre class="wp-block-preformatted"><strong>Add a dependency</strong> <br>To start sending traces to zipkin, it’s enough to add a dependency to your project .<br>     ● spring-cloud-starter-sleuth <br>     ● spring-cloud-starter-zipkin <br><br><strong>Setup app fro ZIPKIN</strong><br>You can provide additional configuration options to adjust sampling, zipkin base url where your zipkin server is deployed, etc.<br>   ● Sampling probability<br>   ● Zipkin service base url<br>   ● Zipkin service name <br><br><strong>Observe</strong><br>Sleuth adds tracing context propagation, log correlation and span sending to Zipkin compatible servers.<br>   ● Now Zipkin can give view of traces and spans <br>   ● You can also view all the latencies. </pre>



<figure class="wp-block-image alignwide"><img data-attachment-id="56" data-permalink="https://aviteshdocs.wordpress.com/zipkin-di-2/" data-orig-file="https://aviteshdocs.files.wordpress.com/2019/02/zipkin-di-2.png?w=1100" data-orig-size="930,484" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="zipkin-di-2" data-image-description="" data-medium-file="https://aviteshdocs.files.wordpress.com/2019/02/zipkin-di-2.png?w=1100?w=300" data-large-file="https://aviteshdocs.files.wordpress.com/2019/02/zipkin-di-2.png?w=1100?w=930" src="https://aviteshdocs.files.wordpress.com/2019/02/zipkin-di-2.png?w=1100" alt="" class="wp-image-56" srcset="https://aviteshdocs.files.wordpress.com/2019/02/zipkin-di-2.png 930w, https://aviteshdocs.files.wordpress.com/2019/02/zipkin-di-2.png?w=150 150w, https://aviteshdocs.files.wordpress.com/2019/02/zipkin-di-2.png?w=300 300w, https://aviteshdocs.files.wordpress.com/2019/02/zipkin-di-2.png?w=768 768w" sizes="(max-width: 930px) 100vw, 930px" /></figure>



<p>Once we add Sleuth and configure zipkin in our client service, our service starts sending traces to ZIPKIN, it can be done using HTTP methods or using messaging clients also like KAFKA or RabbitMQ depends on implementation you want to use. ZIPKIN has Collector who receive all the spans and store that in span store which could be any DB you configured with ZIPKIN  <br>include in-memory, JDBC (mysql), Cassandra, and Elasticsearch.  Another important component ZIPKIN have is ZIPKIN UI where we can see all the traces and latency for services, which is being fetched form DB using Query server in between.</p>



<div class="wp-block-image"><figure class="aligncenter is-resized"><img data-attachment-id="59" data-permalink="https://aviteshdocs.wordpress.com/keep-calm-it-is-demo-time/" data-orig-file="https://aviteshdocs.files.wordpress.com/2019/02/keep-calm-it-is-demo-time.png?w=305&#038;h=355" data-orig-size="600,700" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="keep-calm-it-is-demo-time" data-image-description="" data-medium-file="https://aviteshdocs.files.wordpress.com/2019/02/keep-calm-it-is-demo-time.png?w=305&#038;h=355?w=257" data-large-file="https://aviteshdocs.files.wordpress.com/2019/02/keep-calm-it-is-demo-time.png?w=305&#038;h=355?w=600" src="https://aviteshdocs.files.wordpress.com/2019/02/keep-calm-it-is-demo-time.png?w=305&#038;h=355" alt="" class="wp-image-59" width="305" height="355" srcset="https://aviteshdocs.files.wordpress.com/2019/02/keep-calm-it-is-demo-time.png?w=305&amp;h=355 305w, https://aviteshdocs.files.wordpress.com/2019/02/keep-calm-it-is-demo-time.png?w=129&amp;h=150 129w, https://aviteshdocs.files.wordpress.com/2019/02/keep-calm-it-is-demo-time.png?w=257&amp;h=300 257w, https://aviteshdocs.files.wordpress.com/2019/02/keep-calm-it-is-demo-time.png 600w" sizes="(max-width: 305px) 100vw, 305px" /></figure></div>



<p></p>



<p>Now i am going to demo the Sleuth with ZIPKIN. And I am going to use our same Student Clearance Microservices. </p>



<p><strong>STEP 1:</strong> DEPLOY ZIPKIN as app in PCF.</p>



<pre class="wp-block-preformatted">To do that we have to download zipkin jar from  <a href="https://search.maven.org/remote_content?g=io.zipkin.java&amp;a=zipkin-server&amp;v=LATEST&amp;c=exec">https://search.maven.org/remote_content?g=io.zipkin.java&amp;a=zipkin-server&amp;v=LATEST&amp;c=exec</a> , which is by default using in memory database.</pre>



<p><strong>STEP 2: </strong>Configure services to use Sleuth and ZIPKIN.</p>



<pre class="wp-block-preformatted"><code><strong>POM : </strong></code><strong><br></strong><code>&lt;dependency&gt;         </code><br><code>   &lt;groupId&gt;org.springframework.cloud&lt;/groupId&gt; </code><br><code>   &lt;artifactId&gt;spring-cloud-starter-zipkin&lt;/artifactId&gt;     &lt;/dependency&gt;</code><br><code>&lt;dependency&gt;</code><br><code>   &lt;groupId&gt;org.springframework.cloud&lt;/groupId&gt;</code><br><code>   &lt;artifactId&gt;spring-cloud-starter-sleuth&lt;/artifactId&gt;     &lt;/dependency&gt;</code><br><br><strong>application.properties : </strong><br>spring.sleuth.sampler.probability = 1.0<br>spring.zipkin.baseUrl = https://zipkin-avitesh.cfapps.io/<br>spring.zipkin.service.name=financeClearance<br>spring.zipkin.sender.type=web<br></pre>



<p>NOTE : Same above configuration i have done in each services. My zipkin was deployed in PCF and thats route was <a href="https://zipkin-avitesh.cfapps.io" rel="nofollow">https://zipkin-avitesh.cfapps.io</a>. and i am using WEB i.e. http method for sending traces.</p>



<p><strong>STEP 3:</strong> Add Custom span</p>



<pre class="wp-block-preformatted">@NewSpan("clearanceDataChecker")<br>public String clearanceDataChecker(@SpanTag("clearanceDataCheck") String tag, int studentId) {<br>   try {<br>      String response = getFinanceClearanceStatus() + " , " +      <br>      getLibraryClearanceStatus();<br>       return response;<br>   } catch (Exception e) {<br>        log.error("Exception occurred while trying to fetch                       <br>        clearancedata", e);<br>        throw new RuntimeException(e);<br>   }<br> }</pre>



<p>I am going to add one custom span in each service&#8217;s method.  Above method i  have added in my controller class and i did the same in each service and named them as *DataChecker.</p>



<p><strong>STEP 4: </strong>Deploy services in PCF</p>



<figure class="wp-block-image alignwide"><img data-attachment-id="60" data-permalink="https://aviteshdocs.wordpress.com/appmanager/" data-orig-file="https://aviteshdocs.files.wordpress.com/2019/02/appmanager.png?w=1100" data-orig-size="998,386" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="appmanager" data-image-description="" data-medium-file="https://aviteshdocs.files.wordpress.com/2019/02/appmanager.png?w=1100?w=300" data-large-file="https://aviteshdocs.files.wordpress.com/2019/02/appmanager.png?w=1100?w=998" src="https://aviteshdocs.files.wordpress.com/2019/02/appmanager.png?w=1100" alt="" class="wp-image-60" srcset="https://aviteshdocs.files.wordpress.com/2019/02/appmanager.png 998w, https://aviteshdocs.files.wordpress.com/2019/02/appmanager.png?w=150 150w, https://aviteshdocs.files.wordpress.com/2019/02/appmanager.png?w=300 300w, https://aviteshdocs.files.wordpress.com/2019/02/appmanager.png?w=768 768w" sizes="(max-width: 998px) 100vw, 998px" /><figcaption> <br>I pushed all of my services and zipkin in PCF.  </figcaption></figure>



<h4>Now i will curl my student clearance service.</h4>



<pre class="wp-block-preformatted">curl https://studentclearance.cfapps.io/getclearance<br><br>RESPONSE :  <br>Hold from Fee department , Clear from Transport department , Hold from Library department </pre>



<p>So i received the response from all the underlying services. </p>



<h4>Lets go to ZIPKIN UI and check. </h4>



<p> I will take the route of zipkin from my PCF and enter the same in browser.</p>



<figure class="wp-block-image alignwide"><img data-attachment-id="62" data-permalink="https://aviteshdocs.wordpress.com/zipkin-home/" data-orig-file="https://aviteshdocs.files.wordpress.com/2019/02/zipkin-home.png?w=1100" data-orig-size="1045,358" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="zipkin-home" data-image-description="" data-medium-file="https://aviteshdocs.files.wordpress.com/2019/02/zipkin-home.png?w=1100?w=300" data-large-file="https://aviteshdocs.files.wordpress.com/2019/02/zipkin-home.png?w=1100?w=1024" src="https://aviteshdocs.files.wordpress.com/2019/02/zipkin-home.png?w=1100" alt="" class="wp-image-62" srcset="https://aviteshdocs.files.wordpress.com/2019/02/zipkin-home.png 1045w, https://aviteshdocs.files.wordpress.com/2019/02/zipkin-home.png?w=150 150w, https://aviteshdocs.files.wordpress.com/2019/02/zipkin-home.png?w=300 300w, https://aviteshdocs.files.wordpress.com/2019/02/zipkin-home.png?w=768 768w, https://aviteshdocs.files.wordpress.com/2019/02/zipkin-home.png?w=1024 1024w" sizes="(max-width: 1045px) 100vw, 1045px" /><figcaption>ZIPKIN Home Page</figcaption></figure>



<p style="text-align:center;">This is our ZIPKIN home page and as you see we are able to see all our services in available service list with zipkin. Point to remember here is adding zipkin configuration in service wont be sufficient to see it here in UI, service should have processed at least one request and as part of that sent at least a trace to zipkin.  From this screen we can select any service and view the traces for that particular one. </p>



<h4>Lets check trace for any one service.</h4>



<p>i selected studentClearance service and clicked on Find Traces button there. </p>



<figure class="wp-block-image alignwide"><img data-attachment-id="63" data-permalink="https://aviteshdocs.wordpress.com/selzip/" data-orig-file="https://aviteshdocs.files.wordpress.com/2019/02/selzip.png?w=1100" data-orig-size="980,333" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="selzip" data-image-description="" data-medium-file="https://aviteshdocs.files.wordpress.com/2019/02/selzip.png?w=1100?w=300" data-large-file="https://aviteshdocs.files.wordpress.com/2019/02/selzip.png?w=1100?w=980" src="https://aviteshdocs.files.wordpress.com/2019/02/selzip.png?w=1100" alt="" class="wp-image-63" srcset="https://aviteshdocs.files.wordpress.com/2019/02/selzip.png 980w, https://aviteshdocs.files.wordpress.com/2019/02/selzip.png?w=150 150w, https://aviteshdocs.files.wordpress.com/2019/02/selzip.png?w=300 300w, https://aviteshdocs.files.wordpress.com/2019/02/selzip.png?w=768 768w" sizes="(max-width: 980px) 100vw, 980px" /></figure>



<p style="text-align:left;">We can see the available 1 trace with studentClearance service which has total 14 spans.  We can also see time taken for request to get processed, all the child services involved and their response time too here. </p>



<h4>Now lets see whats more in this trace.</h4>



<p>Will click on available trace to expand the trace even more.</p>



<figure class="wp-block-image alignwide"><img data-attachment-id="65" data-permalink="https://aviteshdocs.wordpress.com/tracezip-1/" data-orig-file="https://aviteshdocs.files.wordpress.com/2019/02/tracezip-1.png?w=1100" data-orig-size="1546,441" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="tracezip-1" data-image-description="" data-medium-file="https://aviteshdocs.files.wordpress.com/2019/02/tracezip-1.png?w=1100?w=300" data-large-file="https://aviteshdocs.files.wordpress.com/2019/02/tracezip-1.png?w=1100?w=1024" src="https://aviteshdocs.files.wordpress.com/2019/02/tracezip-1.png?w=1100" alt="" class="wp-image-65" srcset="https://aviteshdocs.files.wordpress.com/2019/02/tracezip-1.png?w=1100 1100w, https://aviteshdocs.files.wordpress.com/2019/02/tracezip-1.png?w=150 150w, https://aviteshdocs.files.wordpress.com/2019/02/tracezip-1.png?w=300 300w, https://aviteshdocs.files.wordpress.com/2019/02/tracezip-1.png?w=768 768w, https://aviteshdocs.files.wordpress.com/2019/02/tracezip-1.png?w=1024 1024w, https://aviteshdocs.files.wordpress.com/2019/02/tracezip-1.png 1546w" sizes="(max-width: 1100px) 100vw, 1100px" /></figure>



<p>Now we have even more detailed trace information for that particular call. Now we can visualize the latency for each service calls and see their response time. If you notice here all of my service have 2 spans here one is RestTemplate span which is automatically generated and another one is *-checker named which i created by myself to trace the latency for particular method.</p>



<h4>Span Deep dive</h4>



<p>i can even click on any span there and see its details like below.</p>



<figure class="wp-block-image alignwide"><img data-attachment-id="66" data-permalink="https://aviteshdocs.wordpress.com/span/" data-orig-file="https://aviteshdocs.files.wordpress.com/2019/02/span.png?w=1100" data-orig-size="599,387" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="span" data-image-description="" data-medium-file="https://aviteshdocs.files.wordpress.com/2019/02/span.png?w=1100?w=300" data-large-file="https://aviteshdocs.files.wordpress.com/2019/02/span.png?w=1100?w=599" src="https://aviteshdocs.files.wordpress.com/2019/02/span.png?w=1100" alt="" class="wp-image-66" srcset="https://aviteshdocs.files.wordpress.com/2019/02/span.png 599w, https://aviteshdocs.files.wordpress.com/2019/02/span.png?w=150 150w, https://aviteshdocs.files.wordpress.com/2019/02/span.png?w=300 300w" sizes="(max-width: 599px) 100vw, 599px" /></figure>



<h4><strong>Zipkin Dependency Screen</strong></h4>



<p>I will click on Dependencies tab available in ZIPKIN home page.</p>



<figure class="wp-block-image alignwide"><img data-attachment-id="67" data-permalink="https://aviteshdocs.wordpress.com/dep/" data-orig-file="https://aviteshdocs.files.wordpress.com/2019/02/dep.png?w=1100" data-orig-size="995,373" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="dep" data-image-description="" data-medium-file="https://aviteshdocs.files.wordpress.com/2019/02/dep.png?w=1100?w=300" data-large-file="https://aviteshdocs.files.wordpress.com/2019/02/dep.png?w=1100?w=995" src="https://aviteshdocs.files.wordpress.com/2019/02/dep.png?w=1100" alt="" class="wp-image-67" srcset="https://aviteshdocs.files.wordpress.com/2019/02/dep.png 995w, https://aviteshdocs.files.wordpress.com/2019/02/dep.png?w=150 150w, https://aviteshdocs.files.wordpress.com/2019/02/dep.png?w=300 300w, https://aviteshdocs.files.wordpress.com/2019/02/dep.png?w=768 768w" sizes="(max-width: 995px) 100vw, 995px" /></figure>



<p>Now this is very cool feature in zipkin where we can visually see the service calls design, things to notice here is connecting line darkness depends on the usage of service. If there is any error happening between services, that particular line will go red. So in above finance service was using transportservice and feeService more than others so that&#8217;s darker than other.</p>



<h2>Conculsion</h2>



<p>So from now, no more grepping logs from all the tons of services and banging head on complex tools to find the latency and delay cause.</p>



<h2>Thank you for reading this.</h2>




</body>
</html>
