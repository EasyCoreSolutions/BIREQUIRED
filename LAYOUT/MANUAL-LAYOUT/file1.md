
# 설정파일 옵션

BI-REQUIRED! 를 사용하기 위해서는 설정파일(LAYOUT)을 설정해야 합니다.

```json
{						
	Layout: {					
		info: "정보영역-텍스트",			---	옵션바에서 정보로 보여줄 내용을 작성하는곳입니다.
		title: "타이틀영역-텍스트",				
		grand_total_percent: true,				
		menu_nav: "expended",								
		charts: {				
			charts_config: "pie-sankey.json",			
			show: true,			
			template_list: "0_layout_list.json"			
		},				
		table_display: true,				
		expanded_collapsed_mode: true,				
		transpose: false,				
		total_first: true,				
		error_value: "오류",				
		excelfile: "excel_pivot_table_data",				
		rows: [				
			CustType,			
			AgeGroup			
		],				
		columns: [				
			Gender			
		],				
		values: [				
			{			
				field: "SalesCount",		
				op: "sum",		
				precision: ""		
			},			
			{			
				field: "SalesAmt",		
				op: "sum",		
				precision: ""		
			}			
		],				
		calculated: [				
			{			
				fieldheader: "Response(%)",		
				calculatedname: "responseRate",		
				formula: "ResponseCount / ContactCount * 100",		
				precision: ".00",		
				surfix: "%",		
				error_value: "calcu error code"		
			},			
			{			
				fieldheader: "Offer(%)",		
				calculatedname: "OfferRate",		
				formula: "OfferCount / ContactCount * 100",		
				precision: ".00",		
				surfix: "%",		
				error_value: "calcu error code"		
			}			
		],				
		thousand_delimeter: ",",				
		blank_text: "(blank)",				
		selectcolor: "#999999",				
		columntotal: {				
			show: true,			
			label: "합계"			
		},				
		subtotal: {				
			show: false,			
			label: "소계"			
		},				
		grandtotal: {				
			show: true,			
			label: "총계"			
		},				
		Slicer_display: "expanded",				
		percentage: [				
			{			
				field: "SalesCount",		
				option: "BYGRANDTOTAL",		
				precision: ".00",		
				surfix: "(%)"		
			}			
		],				
		formatting: [				
			{			
				field: "SalesCount",		
				type: "bar",		
				option: "#ff555a"		
			},			
			{			
				field: "SalesAmt",		
				type: "map",		
				option: "#ffff00"		
			},			
			{			
				field: "ContactCount",		
				type: "icons",		
				option: "5-arrows"		
			}			
		],				
		themes: [				
			{			
				name: "ghostwhite",		
				class: "ghostwhite-theme"		
			},			
			{			
				name: "lightblue",		
				class: "lightblue-theme"		
			},			
			{			
				name: "lightgrey",		
				class: "lightgrey-theme"		
			},			
				.		
				.		
				.		
		],				
		set_theme: "lightblue",				
		slicer: {				
			position: "top",			
			fields: [			
				{		
					field: "Gender",	
					size: 5	
				}		
			]			
		},				
		column_sorting: [				
			{			
			   "fieldname": "AGE",			
			   "sorttype": "DESC"			
			}			
		],				
		backGroundhighlight: [				
			{			
				field: "responseRate",		
				color: "#28a745",		
				condition: [		
					between 22 and 25	
				]		
			}			
		],				
		foreGroundhighlight: [				
			{			
				field: "ContactCount",		
				color: "#ff0000",		
				condition: [		
					>1000	
				]		
			}			
		]				
	}					
}						

```

