
# 차트파일 설정

차트의 구성은 두가지 설정으로 구분될 수 있습니다.<br>

첫번째는 동적으로 차트를 변경 할 수 있는 차트의 종류를 지정하는 방법입니다.<br>
두번째는 대시보드를 설정하는 json 설정 파일에 지정하는 방법입니다.<br>

<br>
<br>
<br>

### 1. 차트파일등록

데이터의 종류에 맞게 필요한 차트 종류들을 미리 등록하여 사용자가 동적으로 다양한 차트들로 시각화를 할 수 있습니다.<br>

- Chart-Layout-Builder로 사전에 만든 차트 파일을 "json/chart_layout/" 에 저장합니다.
- "0_layout_list.json" 파일에 차트의 종류를 지정합니다.
- 옵션설정파일 "template_list" 부분에 템플릿 리스트를 적용하여, 레포트마다 다른 차트들을 변경할 수 있게 할 수 있습니다.

<br>

아래는 Chart-Layout-Builder로 만든 ***파이차트와 생키차트를 만드는 json 파일의 구성***입니다.<br>
Chart-Layout-Builder 매뉴얼 페이지 바로가기<br>

```json
{					
	"tabs": [
		{
			"charts": [
				{
					"type": "pie",									
					"xAxis": "@@FIELD1@@",						
					"yAxis": "@@VALUE1@@",						
					"width": "col-md-6 col-lg-6",					
					"height": "300px",								
					"lazyRendering": false,						
					"initialText": "",							
					"options": "",									
					"customOptions": [							
					],
					"css": ""
				},
				{
					"type": "sankey",								
					"xAxis": "@@FIELD1@@",
					"yAxis": "@@VALUE1@@",
					"width": "col-md-12 col-lg-12",
					"chartHeight": "300px",
					"height": "300px",
					"title": "",
					"lazyRendering": false,
					"detailLink": false,
					"caption": "",
					"initialText": "",
					"customOptions": [
					],
					"css": "",
					"dimension": [	
						@@FIELD1@@,							
						@@FIELD2@@,							
						@@FIELD3@@							
					]
				}
			],
			"border":  false
		}
	]
}
```

<br><br>

차트파일을 "json/chart_layout/" 에 저장합니다.<br>이렇게 미리 만들어놓은 다양한 차트의 JSON파일을 "0_layout_list.json" 에 지정합니다.<br>
아래는 "0_layout_list.json" 파일의 json 구성입니다. <br>

```json
{
	"One layout": [
		{
			"name": "파이차트",
			"json": "pie.json"
		},
		{
			"name": "파이-막대차트",
			"json": "pie-bar.json"
		},
		{
			"name": "파이-생키차트",
			"json": "pie-sankey.json"
		}
	]
}
```

<p align="center"><font size="2m">위에서 만든 파이-생키 JSON 파일을 등록</font></p>

<br><br>

***"0_layout_list.json" 파일을 설정파일 "template_list" 부분에 등록***하여 다양한 차트를 동적으로 시각화 할 수 있습니다.<br>
아래는 설정파일 ( Layout.json ) 의 "charts" 부분입니다.<br>

```json
{
	"Layout": {
		"info": ,
		"title": ,
		"grand_total_percent": false,
		"menu_nav": "expanded",
		"charts": {					
            "charts_config": "pie-sankey.json",					
            "show": true,					
            "template_list": "0_layout_list.json"					
            },		
```

