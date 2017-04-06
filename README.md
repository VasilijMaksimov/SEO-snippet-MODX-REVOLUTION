# SEO-snippet-MODX-REVOLUTION
SEO snippet for MODX REVOLUTION

RU/
Подключаем вызов сниппета:
EN/
Connect the call to the snippet:

<title>[[seoTitleCategory]]</title>


RU/
Сниппет:
EN/
Snippet:

<?php
$pagetitle = $modx->resource->get("pagetitle");
$longtitle = $modx->resource->get("longtitle");
$seotitle = $modx->resource->getTVValue("seoTitle");
$seotitlecategory = $modx->resource->getTVValue("seoTitleCategory");
$title = $pagetitle." цена, описание, фото | ".$pagetitle." в интернет магазине Одежды";
$title1 = $longtitle." цена, описание, фото | ".$seotitlecategory." в интернет магазине Одежды";
$title2 = $seotitlecategory." цена, описание, фото | ".$seotitlecategory." в интернет магазине Одежды";

$v = '';
if($seotitle != ''){
 $v = $seotitle;
}
else if ($longtitle != "") {
 $v = $title1;
}
else if ($seotitlecategory != "") {
 $v = $title2;
}
else {
 $v = $title;
}

return $v;
