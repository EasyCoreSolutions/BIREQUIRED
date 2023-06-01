
# 설정파일 옵션

BI-REQUIRED! 를 사용하기 위해서는 JSON 으로 구성된 설정파일 ( Layout )을 설정해야 합니다.<br>
이 레이아웃 설정에 따라서 BI-REQUIRED 를 좀 더 사용자 친화적으로 만들어서 상황과 목적에 맞게 적절하게 사용할 수 있습니다.

설정파일의 옵션을 확인해보고, 적용하여 다양한 기능을 알아보겠습니다.

Layout

info : "정보영역-텍스트"
title : "타이틀영역-텍스트"
grand_total_percent : true
menu_nav : 오른쪽에 보여지는 옵션핸들러 ( 탭 )을 확장하여 보여줍니다. ( expanded ,collapsed, hidden )
charts : BI-Required 에서의 차트 영역
			charts_config : 대시보드가 로딩될때 보여지는 기본 차트 설정파일명
charts_config_json : BI-Required Chart Layout Builder 에서 생성된 차트 JSON 설정값

show : 대시보드에서 차트 기능을 사용할지 여부
template_list : 0_layout_list.json

table_display : 피벗테이블을 대시보드에서 사용할지 여부를 나타냅니다.

```json

	"Layout": {
		"info": "정보영역-텍스트",	    			옵션바에서 정보로 보여줄 내용을 작성하는곳입니다.
		"title": "타이틀영역-텍스트",	            대시보드 타이틀로 보여질 항목을 작성하는 곳 입니다. HTML-TAG를 지원합니다.
		"grand_total_percent": true,			  피벗테이블의 전체합에서 비율을 포함하여 보여줍니다.
		"menu_nav": "expended",					 오른쪽에 보여지는 옵션핸들러를 확장하여 보여줍니다.
											   (expanded/collapsed/hidden) (펼치기/접기/숨기기) 
		"charts": {								    대시보드에서 차트옵션을 기술합니다.
			"charts_config": "pie-sankey.json",		← 대시보드가 로딩될때 보여지는 기본 차트설정입니다.
			"show": true,						  ← 대시보드에서 차트기능을 사용할지를 나타냅니다.
			"template_list": "0_layout_list.json"	← 대시보드에서 사용 가능한 차트템플릿 목록을 기술합니다.	
		},
		"table_display": true,				      피벗테이블을 대시보드에서 사용 할 것인지를 기술합니다.
		"expanded_collapsed_mode": true,		   피벗테이블모드가 항목-확장 기능을 사용 할 것인지를 나타냅니다.
		"transpose": false,						분석필드를 측정기준으로 사용 할 것인지를 나타냅니다.
		"total_first": true,					합계옵션에서 합계를 먼저 보일것인지를 기술합니다.
		"error_value": "오류",				   피벗테이블 계산 오류 발생시 표시되는 텍스트입니다.	
		"excelfile": "excel_pivot_table_data",	  피벗테이블 내용을 다운로드시 사용되는 기본 파일명입니다.
		"rows": [								피벗테이블의 열항목으로 사용될 필드명을 기술합니다.
			"CustType",							← 최대 3개의 필드명을 사용 할 수 있습니다.
			"AgeGroup"
		],
		"columns": [							피벗테이블의 컬럼영역에 보여질 필드를 설정합니다.
			"Gender"							← 최대 2개의 필드를 설정 할 수 있습니다.
		],
		"values": [								피벗테이블의 수치형 필드를 설정합니다.
			{								   수치형필드의 개수는 제한이 없습니다.
				"field": "SalesCount",			← 필드명을 설정합니다.
				"op": "sum",				   ← 계산유형을 설정 합니다. (예시 : Sum/Avg)
				"precision": ""										← 계산시 소수점 자리를 설정합니다. (.0,.00)
			},
			{
				"field": "SalesAmt",
				"op": "sum",
				"precision": ""
			}
		],
		"calculated": [												피벗테이블에서 사용하는 계산값을 설정합니다.
			{
				"fieldheader": "Response(%)",						← 필드명 
				"calculatedname": "responseRate",					← 계산값필드명
				"formula": "ResponseCount / ContactCount * 100",	← 계산식 
				"precision": ".00",									← 소수점 위치
				"surfix": "%",										← 계산된 값과 표시되는 텍스트
				"error_value": "calcu error code"					← 오류발생시 보여지는 텍스트
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
		"thousand_delimeter": ",",									천단위 구분자
		"blank_text": "(blank)",									데이터가 없는 경우 보여지는 텍스트입니다.
		"selectcolor": "#999999",									피벗테이블 셀 선택시 보여지는 색상입니다.
		"columntotal": {											컬럼합계 옵션
			"show": true,											← 컬럼합계를 보여줍니다.
			"label": "합계"											← 컬럼합계 레이블
		},
		"subtotal": {												첫번째 항목에 대한 소계 옵션입니다.
			"show": false,											← 소계를 보여줍니다.
			"label": "소계"											← 소계 레이블
		},
		"grandtotal": {												전체합 옵션을 설정합니다.
			"show": true,											← 전체합을 보여줄것인지를 설정합니다.
			"label": "총계"											← 전체합 레이블
		},
		"Slicer_display": "expanded",
		"percentage": [												피벗테이블의 수치형 필드에 대하여 퍼센트(%) 적용하는 옵션
			{
				"field": "SalesCount",								← 대상필드명
				"option": "BYGRANDTOTAL",							← 옵션 (전체합대비 퍼센트, 열합대비, 컬럼합대비, 부분합대비 퍼센트지정)
				"precision": ".00",									← 소수점자리
				"surfix": "(%)"										← 미주텍스트
			}
		],
		"formatting": [												피벗테이블 수치형 필드에 대한 포맷팅 옵션입니다.
			{
				"field": "SalesCount",								← 대상필드명
				"type": "bar",										← 바타입 표시 (바타입, 히트맵타입, 아이콘타입)
				"option": "#ff555a"									← 표현색상
			},
			{
				"field": "SalesAmt",								← 대상필드명
				"type": "map",										← 히트맵으로 표시
				"option": "#ffff00"									← 표현색상
			},			
			{			
				"field": "ContactCount",							← 대상필드명
				"type": "icons",									← 아이콘으로 표시
				"option": "5-arrows"								← 아이콘유형
			}
		],	
		"themes": [													피벗테이블 테마목록
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
			},
				.
				.
				.
		],
		"set_theme": "lightblue",									기본 피벗테이블 테마명
		"slicer": {													피벗테이블 슬라이서  설정
			"position": "top",										← 피벗테이블 위치 설정 ( top,left,right,bottom,hidden )
			"fields":												← 대상필드 설정
				{
					"field": "Gender",								← Gender필드를 슬라이서로 사용
					"size": 5										← 항목은 최대 5개를 표시
				}
			]
		},
		"column_sorting": [											정렬항목을 설정합니다.
			{
			   "fieldname": "AGE",									← 필드명
			   "sorttype": "DESC"									← 정렬타입
			}
		],
		"backGroundhighlight": [									피벗테이블 셀의 백그라운드 색상을 설정합니다.	
			{
				"field": "responseRate",							← 대상 필드명
				"color": "#28a745",									← 색상
				"condition": [										← 표시되는 조건 : 값이 22-25이면 색상표현됩니다.
					"between 22 and 25"
				]
			}
		],	
		"foreGroundhighlight": [									피벗테이블 셀의 폰트 색상을 설정합니다.
			{
				"field": "ContactCount",							← 대상 필드명
				"color": "#ff0000",									← 색상
				"condition": [										← 표시되는 조건 : 값이 1000이상이면 글자색을 변경합니다.
					>1000
				]
			}
		]
	}
}

```



