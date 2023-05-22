
# 설정파일 옵션

BI-REQUIRED! 를 사용하기 위해서는 설정파일(LAYOUT)을 설정해야 합니다.

```json
Layout: {														
	info: "정보영역-텍스트",	   - 옵션바에서 정보로 보여줄 내용을 작성하는곳입니다.						
	title: "타이틀영역-텍스트",	  - 대시보드 타이틀로 보여질 항목을 작성곳입니다. HTML-TAG를 지원합니다.						
	grand_total_percent: true,	- 피벗테이블의 전체합에서 비율을 포함하여 보여줍니다.						
	menu_nav: "expended",	    - 오른쪽에 보여지는 옵션핸들러를 확장하여 보여줍니다. (expanded/collapsed/hidden) (펼치기/접기/숨기기) 						
	charts: {	대시보드에서 차트옵션을 기술합니다.						
		charts_config: "pie-sankey.json",	-  대시보드가 로딩될때 보여지는 기본 차트설정입니다.						
		show: true,						  -  대시보드에서 차트영역을 사용할지를 나타냅니다.						
		template_list: "0_layout_list.json"	-  대시보드에서 사용 가능한 차트템플릿 목록을 기술합니다.						
	},													

```

