
# 설정파일 옵션

BI-REQUIRED! 를 사용하기 위해서는 JSON 으로 구성된 설정파일 ( 하단 JSON 형식 ) 을 설정해야 합니다.<br>

이 레이아웃 설정에 따라서 BI-REQUIRED 를 좀 더 사용자 친화적으로 만들어서 상황과 목적에 맞게 적절하게 사용할 수 있습니다.<br>

설정 파일의 옵션을 확인해보고, 적용하여 다양한 기능을 알아보겠습니다. 
<br>
<br>

```json
{
	"Layout": {
		"info": "정보영역-텍스트",
		"title": "타이틀영역-텍스트",
		"grand_total_percent": true,
		"menu_nav": "expended",
		"charts": {
			"charts_config": "pie-sankey.json",
			"show": true,
			"template_list": "0_layout_list.json"
		},
		"table_display": true,
		"expanded_collapsed_mode": true,
		"transpose": false,
		"total_first": true,
		"error_value": "오류",
		"excelfile": "excel_pivot_table_data",
		"rows": [
			"CustType",
			"AgeGroup"
		],
		"columns": [
			"Gender"
		],
		"values": [
			{
				"field": "SalesCount",
				"op": "sum",
				"precision": ""
			},
			{
				"field": "SalesAmt",
				"op": "sum",
				"precision": ""
			}
		],
		"calculated": [
			{
				"fieldheader": "Response(%)",
				"calculatedname": "responseRate",
				"formula": "ResponseCount / ContactCount * 100",
				"precision": ".00",
				"surfix": "%",
				"error_value": "calcu error code"
			},
			{
				"fieldheader": "Offer(%)",
				"calculatedname": "OfferRate",
				"formula": "OfferCount / ContactCount * 100",
				"precision": ".00",
				"surfix": "%",
				"error_value": "calcu error code"
			}
		],
		"thousand_delimeter": "",
		"blank_text": "(blank)",
		"selectcolor": "#999999",
		"columntotal": {
			"show": true,
			"label": "합계"
		},
		"subtotal": {
			"show": false,
			"label": "소계"
		},
		"grandtotal": {
			"show": true,
			"label": "총계"
		},
		"Slicer_display": "expanded",
		"percentage": [
			{
				"field": "SalesCount",
				"option": "BYGRANDTOTAL",
				"precision": ".00",
				"surfix": "(%)"
			}
		],
		"formatting": [
			{
				"field": "SalesCount",
				"type": "bar",
				"option": "#ff555a"
			},
			{
				"field": "SalesAmt",
				"type": "map",
				"option": "#ffff00"
			},
			{
				"field": "ContactCount",
				"type": "icons",
				"option": "5-arrows"
			}
		],
		"themes": [
			{
				"name": "ghostwhite",
				"class": "ghostwhite-theme"
			},
			{
				"name": "lightblue",
				"class": "lightblue-theme"
			},
			{
				"name": "lightgrey",
				"class": "lightgrey-theme"
			}
		],
		"set_theme": "lightblue",
		"slicer": {
			"position": "top",
			"fields": [
				{
					"field": "Gender",
					"size": 5
				}
			]
		},
		"column_sorting": [
			{
				"fieldname": "AGE",
				"sorttype": "DESC"
			}
		],
		"backGroundhighlight": [
			{
				"field": "responseRate",
				"color": "#28a745",
				"condition": [
					"between 22 and 25"
				]
			}
		],
		"foreGroundhighlight": [
			{
				"field": "ContactCount",
				"color": "#ff0000",
				"condition": [
					">1000"
				]
			}
		]
	}
}
```
<br>

---

<br>

## 1. Info

우측 옵션 핸들러에서 맨 하단 정보( i ) 탭에서 보일 내용을 작성하는 곳 입니다.<br>
사용자에게 정보를 HTML태그를 이용하여 전달할 수 있습니다.<br>또한 false 값을 만들어 인포탭을 잠금 할 수도 있습니다.<br>

``` json
{
    "Layout": {
		"info": "인포영역에 출력될 내용입니다!",
```

![image-20230602135814923](images/file1/image-20230602135814923.png)

<p align="center"><font size="2m">HTML태그를 사용하여 작성한 정보탭(하단)</font></p>

<br>
<br>

## 2. Title

대시보드 타이틀로 보일 내용을 작성하는 곳입니다.<br>HTML태그를 지원합니다. 인포 옵션과 마찬가지로 false 값을 만들어 대시보드 타이틀을 잠금 할 수도 있습니다.<br>

```json
{
	"Layout": {
		"title":"<h5>타이틀영역에 출력될 내용입니다!<h5>",
```

![image-20230602142724097](images/file1/image-20230602142724097.png)

<p align="center"><font size="2m">HTML태그를 사용하여 작성한 대시보드 타이틀(하단)</font></p>

<br>
<br>

## 3. Grand_total_percent

피벗테이블의 전체합(총계)에서 비율(%)을 계산하여 출력합니다.<br>

```json
{
	"Layout": {
		"grand_total_percent": true,
```

![image-20230602154306942](images/file1/image-20230602154306942.png)

<p align="center"><font size="2m">총계비율(%)출력 (상단피벗테이블 - true 설정), 미출력 (하단피벗테이블 - false 설정)</font></p>

<br>
<br>

## 4. Menu_nav

레포트를 처음 조회했을때 오른쪽에 보여지는 기능탭 ( 옵션핸들러 )을 확장하여 보여주는 옵션입니다. <br>expanded , collapsed , hidden 3가지의 옵션값을 적용할 수 있습니다. <br>

expanded - 기능탭 펼쳐보이기 <br>collapased - 기능탭 접기<br>hidden - 기능탭 비활성화하기<br>

```json
{
    "Layout": {
      "menu_nav": "expended",
```

