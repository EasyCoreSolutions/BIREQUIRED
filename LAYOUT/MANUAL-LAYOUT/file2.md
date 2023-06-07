
# 실행스크립트 및 데이터셋 



## 1. 실행스크립트

BI-REQUIRED! 를 실행하기 위한 스크립트입니다.<br>
"tmpl/demo1.html" 를 의 스크립트를 참조합니다.<br>

| 스크립트            | 내용                                    | 경로                        |
| ------------------- | --------------------------------------- | --------------------------- |
| crosstableFieldUrl: | 사용될 데이터셋 JSON 파일을 지정합니다. | "json/crosstablefield.json" |
| layoutUrl:          | 사용될 설정 JSON파일을 지정합니다.      | "json/Layout.json"          |


```html
<script>

        $('#crosstable2').crosstable2({
            crosstableFieldUrl: "json/crosstablefield.json",
            layoutUrl: "json/Layout.json",
            lang: "kr",
            "more_charts": true
        });
</script>
```

<br>
<br>
<br>

## 2. 데이터셋

기본적으로 데이터구조는 "json/sample_dataset.json" 을 참조하여 동일한 구조로 데이터셋을 생성하여 대입하면 대시보드를 구성 할 수 있습니다.<br>

데이터셋의 구성은 데이터영역과 필드정보영역으로 구분되어 있습니다.<br>

아래는 데이터셋의 일부의 예이며, JSON구조로 되어있습니다.<br><br>

> **"Fields" 영역**

| 구분        | 내용                                                         | 예시           |
| :---------- | ------------------------------------------------------------ | -------------- |
| "FieldName" | 데이터셋의 필드명으로 사용됩니다                             | "CustType"     |
| "FieldDesc" | 필드의 정보를 나타냅니다. ( 대시보드에 출력될 텍스트입니다 ) | "고객분류"     |
| "FieldType" | 필드타입입니다.                                              | "CHAR" / "NUM" |

<br>

> **"Input"영역**

| 구분         | 내용                        | 값        | 타입   |
| :----------- | --------------------------- | --------- | ------ |
| "CustType"   | 필드 영역에서 지정한 필드명 | "General" | "CHAR" |
| "Gender"     | 필드 영역에서 지정한 필드명 | "남자"    | "CHAR" |
| "SalesCount" | 필드 영역에서 지정한 필드명 | "1"       | "NUM"  |
| "SalesAmt"   | 필드 영역에서 지정한 필드명 | "15000"   | "NUM"  |

<br>

```json
{
	"Fields": [	    												
		{
			"FieldName": "CustType",							
			"FieldDesc": "고객분류",								
			"FieldType": "CHAR"									
		},
		{
			"FieldName": "Gender",
			"FieldDesc": "성별",
			"FieldType": "CHAR"	
		},
		{
			"FieldName": "SalesCount",
			"FieldDesc": "건수",
			"FieldType": "NUM”
		},
		{
			"FieldName": "SalesAmt",
			"FieldDesc": "판매금액",
			"FieldType": "NUM"
		}
	],
	"Input": [	 
		{
			"CustType": "General",								
			"Gender": "남자",	
			"SalesCount": 1,
			"SalesAmt": 15000
		}
		{
			"CustType": "General",
			"Gender": "남자",	
			"SalesCount": 0,	
			"SalesAmt": 0
		},
		{
			"CustType": "General",
			"Gender": "남자",	
			"SalesCount": 1,
			"SalesAmt": 30000
		}
	]
```

<br>
<br>
<br>
