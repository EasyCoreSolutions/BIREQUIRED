# CSS 와 MAP API

<br>

BI-REQUIRED! 를 이용하기 위하여 필요한 css 파일은 다음과 같습니다 .<br>

피벗테이블의 테마 CSS 파일을 위치하고, 설정파일옵션에서 지정하여 테마를 언제든지 사용자화 할 수 있습니다.<br>
CSS파일은 "css/theme/" 에 위치합니다.<br>

```html
<link rel="stylesheet" href="css/bootstrap.min.css">
<link rel="stylesheet" href="css/awesome.min.css">
<link rel="stylesheet" href="css/dataTables.bootstrap4.min.css">
<link rel="stylesheet" href="css/responsive.bootstrap4.min.css">
<link rel="stylesheet" type="text/css" href="css/jquery-jvectormap.css">
<link rel='stylesheet' type="text/css" href="css/crosstable.css">

<!--Include Themes Here-->

<link rel="stylesheet" type="text/css" href="css/theme/almond.css">
<link rel="stylesheet" type="text/css" href="css/theme/azure.css">
<link rel="stylesheet" type="text/css" href="css/theme/brown.css">
<link rel="stylesheet" type="text/css" href="css/theme/cosmo.css">
<link rel="stylesheet" type="text/css" href="css/theme/eggplant.css">
<link rel="stylesheet" type="text/css" href="css/theme/flat.css">
<link rel="stylesheet" type="text/css" href="css/theme/granite.css">
<link rel="stylesheet" type="text/css" href="css/theme/lime.css">
<link rel="stylesheet" type="text/css" href="css/theme/navy.css">
<link rel="stylesheet" type="text/css" href="css/theme/silver.css">
<link rel="stylesheet" type="text/css" href="css/theme/yeti.css">
<link rel="stylesheet" type="text/css" href="css/theme/aliceblue.css">
<link rel="stylesheet" type="text/css" href="css/theme/comsilk.css">
<link rel="stylesheet" type="text/css" href="css/theme/ghostwhite.css">
<link rel="stylesheet" type="text/css" href="css/theme/lightblue.css">
<link rel="stylesheet" type="text/css" href="css/theme/lightgrey.css">
```

<br>
<br>
<br>

카카오맵을 사용 할 경우, 카카오맵 API를 등록하여 API키를 발급받아 사용 할 수 있습니다.<br>

발급받은 API키는 다음과 같이 등록하여 사용합니다.<br>

```html
<script type="text/javascript"
	src="//dapi.kakao.com/v2/maps/sdk.js?appkey=d7fed076a12341521631f8efe948480abae&libraries=services,clusterer">
</script>
```

<p align="center"><font size="2m">발급받은 API키 (예시) 를 등록</font></p>