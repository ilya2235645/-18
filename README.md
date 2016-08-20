# -18<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>Верность</title>

<script type="text/javascript" charset="utf-8" src="//s.shadowlands.ru/loyaltyvk-res/c8d946f22cf827ebb9bbb8adf05dadb84b9ccad4lang_strings.js"></script>
<script type="text/javascript" charset="utf-8" src="//s.shadowlands.ru/loyaltyvk-res/a0ae3697b0ab8c0e8bd3186c80db42abd6d97a8djquery.js"></script>


<script src="//vk.com/js/api/xd_connection.js?2" type="text/javascript"></script>


<script type="text/javascript" src="//s.shadowlands.ru/loyaltyvk-res/5847ed101f55d51c53538a7078971e7de8fb6762swfobject.js"></script>
<script type="text/javascript" charset="utf-8" src="//s.shadowlands.ru/loyaltyvk-res/a0ae3697b0ab8c0e8bd3186c80db42abd6d97a8djquery.js"></script>
<script type="text/javascript" charset="utf-8" src="//s.shadowlands.ru/loyaltyvk-res/c8d946f22cf827ebb9bbb8adf05dadb84b9ccad4lang_strings.js"></script>
<link rel="stylesheet" type="text/css" href="//s.shadowlands.ru/loyaltyvk-res/55fb9494c0b678e89f6d0c5790216029592d7a75styles.css" />

<style>
body{ margin: 0px; overflow:hidden; background-color: #FFFFFF;}
a:hover{text-decoration:none};
</style>


<script language="JavaScript" type="text/javascript">
var flashvars = {};





function getQueryVariable(variable) {
    var query = document.location.search.substring(1);

    var vars = query.split("&");

    for (var i=0;i<vars.length;i++) {
        var pair = vars[i].split("=");
        if (pair[0] == variable) {
            return pair[1];
        }
    }
    return 'не определён';
}

function hasQueryVariable(variable) {
    var query = document.location.search.substring(1);

    var vars = query.split("&");
    for (var i=0;i<vars.length;i++) {
        var pair = vars[i].split("=");
        if (pair[0] == variable) {
            return true;
        }
    }
    return false;
}

function showAddToQuickMenu()
{
	VK.callMethod("showSettingsBox",256);
}
$(document).ready(function()
{	
	var buttons;

    var groupLink = 'https://vk.com/vernost_group'

    var lang
	lang = "ru";
	
	
	
	
	buttons = [
		{title:strings[lang].play, id:"play"},
		{title:strings[lang].faq, id:"faq"},
		{title:strings[lang].community, url:groupLink},
		{title:strings[lang].rules, id:"rules"}
	];

	for(var i = 0; i < buttons.length; i++)
	{
		var button = buttons[i];
		$("#logo").append(
		'<a ' + (button.url ? 'target="_blank"' : '') + 'href="' + (button.url ? button.url : 'javascript:void(0);') +
		'" id="' + (button.id ? button.id : '') + '" class="button ' + (i == 0 ? " act" : "") + (button.url ? ' url' : '') +
		'">' + button.title + '</a>'
		);
	}

	$("#header a").click(function(){
		if($(this).hasClass("url"))
		{
			return true;
		}
		

		$("#logo > .act").removeClass("act");
		$(this).addClass("act");

		$("#contents > .act").removeClass("act");
		$("#contents > ." + $(this).attr("id")).addClass("act");
	});
	
	var height = "730px";

	$("#contents > div.faq").append('<iframe src="//s.shadowlands.ru/loyaltyvk-res/faqs/' + lang + '.html" width="100%" frameborder="0" height="' + height + '" align="left"></iframe>');

	$("#contents > div.rules").append('<iframe src="//s.shadowlands.ru/loyaltyvk-res/rules/vk.html" width="100%" frameborder="0" height="' + height + '" align="left"></iframe>');

	$("#group_link").attr("href", groupLink);

});

function getUserId()
{
}


function detectIE() {
    var ua = window.navigator.userAgent;

    // test values
    // IE 10
    //ua = 'Mozilla/5.0 (compatible; MSIE 10.0; Windows NT 6.2; Trident/6.0)';
    // IE 11
    //ua = 'Mozilla/5.0 (Windows NT 6.3; Trident/7.0; rv:11.0) like Gecko';
    // IE 12 / Spartan
    //ua = 'Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/39.0.2171.71 Safari/537.36 Edge/12.0';

    var msie = ua.indexOf('MSIE ');
    if (msie > 0) {
        // IE 10 or older => return version number
        return parseInt(ua.substring(msie + 5, ua.indexOf('.', msie)), 10);
    }

    var trident = ua.indexOf('Trident/');
    if (trident > 0) {
        // IE 11 => return version number
        var rv = ua.indexOf('rv:');
        return parseInt(ua.substring(rv + 3, ua.indexOf('.', rv)), 10);
    }

    var edge = ua.indexOf('Edge/');
    if (edge > 0) {
        // IE 12 => return version number
        return parseInt(ua.substring(edge + 5, ua.indexOf('.', edge)), 10);
    }

    // other browser
    return false;
}

$(document).ready(function()
{

    VK.addCallback("onWindowFocus", onWindowFocus);
    VK.addCallback("onWindowBlur", WindowBlur);

    function WindowBlur()
    {
        document.body.style.visibility = "hidden";
        if(window.navigator.userAgent.indexOf('Firefox') == -1)
		{
    		document.getElementById('game-container').style.position = "absolute";
    		document.getElementById('game-container').style.left = "10000";
    	}
    }

    function onWindowFocus()
    {
    	document.body.style.visibility = "visible";
        if(window.navigator.userAgent.indexOf('Firefox') == -1)
		{
    		document.getElementById('game-container').style.position = "static";
    		document.getElementById('game-container').style.left = "0";
    	}
    }

	VK.init(function() {
		VK.Widgets.Like('vk_like', {width:400, type:'button', pageImage:'http://s.shadowlands.ru/loyaltyvk-res/loyalty_100_63.png', pageTitle:'Верность', pageDescription:'Сражения и Домохозяйство, Семейные ценности и Флирт. Играйте с друзьями и любимыми в Верность.', text:'Сражения и Домохозяйство, Семейные ценности и Флирт. Играйте с друзьями и любимыми в Верность.'});
		VK.Widgets.Subscribe("vk_subscribe", {}, -59391787);
	});

	var url = document.location.toString().split('?');
	var flashdata = "";
	var flashdata = (url[1] ? url[1] : '');

    flashdata += "&swfDigest=" + "d3f418996f128bedbd323494c83c01fb7a921a3d";
    flashdata += "&digestVer=" + "cd24432156d3ec3ff01b62c2e03b3b705476e544";


    var params =
    {
        id: "flashobj",
        width: "1000",
        height: "730",
        allowScriptAccess: 'always',
        allowFullScreen: 'true',
        wmode : 'window',
        browserzoom: 'noscale',
        flashvars: flashdata
    };


	var attributes =
	{
	    id: "flashobj"

	};

    var swfUrl = "//s.shadowlands.ru/loyaltyvk-res/daedaa7e88f51db87a8038c93b15f2d390aa2ad6preloader.swf";
	
	var isIE = detectIE();

    if (isIE)
    {
        params.wmode = "transparent";
    }
    var flashObject;
    var lastVisibilityValue;
    var swfHandler = function handleSwfObjAdded(e)
    {
    }

	swfobject.embedSWF(swfUrl, 'flash-container', "1000", "730", "10.2.0", "1c12004633e89d6de3bbe4a190093a537bdecebeexpressInstall.swf", flashvars , params , attributes, swfHandler);


	
	
});




</script>
</head>

<body scroll="no">


<div id="header">
	<div id="header_in">
		<div id="logo">
		</div>
	</div>
</div>
<div id="contents">
	<div class="play act" align="center">
		<div id="game-container" align="center" align="center" style="position:relative">
			<div id="flash-container">
				<a href="//www.adobe.com/go/getflashplayer">
				<img src="//www.adobe.com/images/shared/download_buttons/get_flash_player.gif" alt="Get Adobe Flash player"/>
				</a>
			</div>
		</div>
	</div>
	<div class="faq" align="center"></div>
	<div class="rules" align="center"></div>
</div>

<div id="uid-container">



	<div id="new_footer">
		<link rel="stylesheet" type="text/css" href="//s.shadowlands.ru/loyaltyvk-res/18422eed5caac5af0a1dae581d604af2648caf1afooter.css">
		<div id="footer_top">
			<div id="left_links">
				<a target="_blank" id="group_link" href="https://vk.com/vernost_group"><img src="//s.shadowlands.ru/loyaltyvk-res/footer/icon_group.png" />Официальная группа</a>
				<a target="_blank" id="faq_link" href="https://vk.com/page-59391787_49218614"><img src="//s.shadowlands.ru/loyaltyvk-res/footer/icon_faq.png" />Справка по игре</a>

			</div>
			<div id="right_links">
				<a target="_blank" title="Добавить игру в меню слева" alt="Добавить игру в меню слева" href="#" id="vk_menu" onclick="showAddToQuickMenu();return false;" href="#"><img src="//s.shadowlands.ru/loyaltyvk-res/footer/icon_add.png" />Добавить в меню</a>
			</div>
		</div>
		<div id="footer_bottom">
		<!-- баннеры  -->
			<link rel="stylesheet" type="text/css" href="//s.shadowlands.ru/loyaltyvk-res/c651dc770f570e525e9ee4a90871f453099a4b95banners.css">
			<script src="//s.shadowlands.ru/loyaltyvk-res/85b593bd3d2977f8a334c6f432299134cd5a5de2banners.js" type="text/javascript"></script>
			<div id="logo_footer"></div>
			<div id="banners">
				<div id="banners_scroll">
					<a class="prev" href="javascript:void(0);"></a>
					<div></div>
					<div id="banners_container">
						<div id="banners_container_in">
						</div>
					</div>
					<a class="next" href="javascript:void(0);"></a>
				</div>
			</div>
		<!-- баннеры  -->

        </div>
	</div>


<div style="padding-top:8px;padding-bottom:18px;padding-left:5px;">
<table border="0" cellpadding="0" cellspacing="0" width="1000" style="margin-top:10px">
<tr>
	<td>
		<div id="vk_like" style="float:left;background-color:transparent;"></div>
	</td>

	<td>
		<div style="float:left;"><div id="vk_subscribe" style="background-color:transparent;"></div></div>
	</td>

	<td>
		<div style="float:right"><a href="https://vk.com/page-59391787_49218614" target="_blank" title="Посмотреть справку по игре"  alt="Посмотреть справку по игре" style="cursor:pointer;"><img src="//s.shadowlands.ru/loyaltyvk-res/c964cdcf5ba1b6bed5207b65a988c38e83c506a3faq.jpg" border="0"></a></div>
	</td>

	<td>
		<a title="Добавить игру в меню слева"  alt="Добавить игру в меню слева" href="#" id="vk_menu" onclick="showAddToQuickMenu();return false;" style="float:right;margin-right:5px;display:block;background:url(//s.shadowlands.ru/loyaltyvk-res/f4c0a67f4db305913cdc58982b870f17c4d199adadd_menu.jpg) 0 0 no-repeat;height:22px;width:122px;"></a>
	</td>
</tr>
</table>
</div>

<form enctype="multipart/form-data" action="" method="post" id="multipartPost" style="visibility:hidden">
</form>

</body>
</html>
