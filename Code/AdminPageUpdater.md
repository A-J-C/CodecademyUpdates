```
/* Main Body */
body {
	background: #1F3F58;
}
div.rebrand div.container {
	font-family: 'DINRoundOT-Light';
	padding-top: 15px;
	padding-bottom: 15px;
}

/* Header */
div.rebrand div.container div.page-header {
	width: 970px;
	margin-bottom: 7.5px;
}
div.rebrand div.container div.page-header h2 {
	color: white;
}
div.rebrand div.container div.page-header h2 small {
	color: whitesmoke;
}
/* Tabs in header */
div.rebrand div.container div.nav div.btn-group {
	width: 250px;
	margin-right: 5px;
}
div.rebrand div.container div.nav div.btn-group a.btn {
	background: #1F3F58;
	color: white;
	border: none;
	font-size: 15px;
	border-right: 1px solid #eee;
	margin-right: 1px;
	box-shadow: none;
	border-radius: 0;
	font-weight: normal;
}
div.rebrand div.container div.nav div.btn-group a.btn:first-child {
	border-left: 1px solid #eee;
}
div.rebrand div.container div.nav div.btn-group a.btn:hover {
	background: #59A1C7;
}

/* Main Content */
/* Activity Stats */
div.rebrand div.container ul#stats {
	width: 540px;
	height: 25px;
	margin: 0;
	padding: 0 215px;
	border-bottom: 0;
	margin-left: 5px;
	padding-top: 5px;
}
div.rebrand div.container ul#stats > h3 {
	color: #d2d2d2;
	font-size: 1.25em;
	position: absolute;
}
div.rebrand div.container ul#stats li:nth-child(2) {
	display: inline-block;
	margin-left: 310px;
	border: none;
	width: 125px;
	padding: 0;
	margin-right: 0;
}
div.rebrand div.container ul#stats li:nth-child(3) {
	padding: 0;
	margin: 0;
	width: 105px;
}
div.rebrand div.container ul#stats li > h2 {
	color: #d2d2d2;
	font-size: 1.25em;
	float: left;
}
div.rebrand div.container ul#stats li > small {
	color: #d2d2d2;
	margin-left: 10px;
}
/* Forums */
div.rebrand div.container div#track-forums, div.rebrand div.container div#track-forums > div.span12 {
	width: 920px;
}
div.rebrand div.container div#track-forums h3.divider a.link_in_h3,
div.rebrand div.container div#track-forums div.row ul.forum_qa_list li div.meta em.timestamp {
	color: #8e8e8e;
	width: auto;
}
div.rebrand div.container div#track-forums h3.divider a.link_in_h3:hover {
	color: white;
}
div.rebrand div.container div#track-forums h3.divider {
	color: white;
}
div.rebrand div.container div#track-forums div.row ul.forum_qa_list li a.title, div.rebrand div.container div#track-forums div.row ul.forum_qa_list li a.entry {
	color: #dddddd;
	width: 62.5%;
	max-width: 62.5%;
}
div.rebrand div.container div#track-forums div.row ul.forum_qa_list li a.title div, div.rebrand div.container div#track-forums div.row ul.forum_qa_list li a.entry div {
	overflow: hidden;
	text-overflow: ellipsis;
}
div.rebrand div.container div#track-forums div.row ul.forum_qa_list li a.title div.hidden_item, div.rebrand div.container div#track-forums div.row ul.forum_qa_list li a.entry div.hidden_item {
	color: #8e8e8e;
}
div.rebrand div.container div#track-forums div.row ul.forum_qa_list > li {
	border-radius: 0;
	border: none;
}
div.rebrand div.container div#track-forums div.row ul.forum_qa_list > li:hover {
	background: #59A1C7;
}
div.rebrand div.container div#track-forums div.row ul.forum_qa_list > li:hover a.title, div.rebrand div.container div#track-forums div.row ul.forum_qa_list li:hover a.title div.hidden_item, div.rebrand div.container div#track-forums div.row ul.forum_qa_list li:hover a.entry, div.rebrand div.container div#track-forums div.row ul.forum_qa_list li:hover a.entry div.hidden_item, div.rebrand div.container div#track-forums div.row ul.forum_qa_list li:hover div.meta em.timestamp {
	color: white;
}
/* Actions button */
div.rebrand div.container div#track-forums div.row ul.forum_qa_list > li div.btn-group a.btn-mini {
	border-radius: 0;
	background: #5d7486;
	border: none;
	box-shadow: none;
	color: white;
	font-weight: normal;
}
div.rebrand div.container div#track-forums div.row ul.forum_qa_list > li div.btn-group ul.dropdown-menu {
	border-radius: 0;
	margin-top: 0px;
	background: #e6e7e8;
	border: none;
	min-width: 125px;
	padding: 0;
}
.icon-remove {
	display: none;
}

/* Page scrolling */
.pagination li:first-child a, .pagination li:last-child a {
	border-radius: 0;
}
.pagination li a, .pagination .active a {
	border: 0;
	color: #59A1C7;
}
.pagination a:hover {
	color: white;
	background: #59A1C7;
}
.pagination .active a:hover, .pagination .active a {
	color: #d2d2d2;
	background: #1F3F58;
}
```

```
$(".admin ul.forum_qa_list>li>a.title, .admin ul.forum_qa_list>li>a.entry").each(function(){
	$(this).attr("target","_blank");
});
```

```
changeText = function(classSelector,oldWord,newWord) {
	if($('.'+classSelector+' .divider').length > 0) {
		$('.'+classSelector+' .divider').html($('.'+classSelector+' .divider').html().replace(oldWord,newWord));
	}
};
changeText('javascript','Javascript','JavaScript');
changeText('jquery','Jquery','jQuery');
changeText('php','Php','PHP');
changeText('apis','Apis','APIs');
```

```
$('.filter:not(.broken)').click(function(){
	$(this).toggleClass('on');
	if($(this).hasClass('on')) {
		$('#track-forums .'+$(this).attr('id')).css('display','block');
	} else {
		$('#track-forums .'+$(this).attr('id')).css('display','none');
	}
});
if($('div.topics ul.forum_qa_list div.pagination.pagination-centered').length > 0) {
	$('#filter_box .filter').css('display','none');
	$('#filter_box').css('padding','0');
}
```

```
<div class='span12' id='filter_box'>
<div id='javascript' class='filter on'> JavaScript </div>
<div id='web' class='filter on'> Web </div>
<div id='jquery' class='filter on'> jQuery </div>
<div id='comments' class='filter on'> All </div>
<div class='filter broken'>
	<a href='/admin/forums/qa/python' title='Opens track questions'>Python</a>
</div>
<div class='filter broken'>
	<a href='/admin/forums/qa/ruby' title='Opens track questions'>Ruby</a>
</div>
<div class='filter broken'>
	<a href='/admin/forums/qa/php' title='Opens track questions'>PHP</a>
</div>
<div class='filter broken'>
	<a href='/admin/forums/qa/apis' title='Opens track questions'>APIs</a>
</div>
</div>
```

```
#filter_box {
	text-align: center;
	margin-bottom: 25px;
	border-bottom: 1px solid #eee;
	margin-left: 0;
	width: 970px;
	margin-top: 5px;
	padding-bottom: 15px;
}
.filter {
	color: whitesmoke;
	background: #1F3F58;
	text-align: center;
	width: 100px;
	display: inline-block;
	border: 1px solid #59A1C7;
}
.filter:hover {
	cursor: pointer;
	background: #39D1B4;
	border: 1px solid #39D1B4;
}
div.on {
	background: #59A1C7;
}
div.on:hover {
	background: #f65a5b;
	border: 1px solid #f65a5b;
}
.filter.broken, .filter {
	background: #1F3F58;
	border: 1px solid #59A1C7;
}
.filter.broken:hover {
	background: #d2d2d2;
	border: 1px solid #d2d2d2;
	color: black;
}
.filter.broken a {
	color: whitesmoke;
	display: inline-block;
	width: 100%;
	font-weight: normal;
}
```

