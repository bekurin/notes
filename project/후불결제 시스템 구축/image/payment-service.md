---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Payment-Service ^q50YdR5t

Ledger-Service ^JVTxdaTg

Mysql ^RHsr4Tlc

payment.success ^myPYhfXq

payment.failure ^dWkDPNPO

Kafka ^v6iMerNv

Settlement-Service ^8i0gw7h8

settlement.success ^ezwmArHN

Client ^DOZVqIbm

scenario#1. payment ^BRt7vuQs

Payment-Service ^Hl6VxnD3

Toss Payment ^2yDPvFHo

Mysql ^doYTOaXY

Client ^zrprptru

1 ^Lu2MJRvo

2 ^6Sl0SAL9

3 ^eFpxFj3m

4 ^lf5QFqSD

5 ^RblQKStJ

6 ^XoO3Mk0l

1. request to payment service
2. payment-service toss the request to connected psp service
3. psp service return the payment result
4. save the result of 3 data to relation database
5. find the saved result
6. return the result of payment status ^5jDABdSQ

Payment-Service ^maejeJHw

Ledger-Service ^jMzzoFJH

Mysql ^0Z54R46u

payment.success ^LxMVRLdj

payment.failure ^I0bBm6jB

Kafka ^3SziCpiJ

1 ^xElyqKDr

2 ^CioNTJZx

3-1 ^iASbu4P8

3-2 ^ugfvqKsS

4 ^e73G2joN

5 ^FR9abEgL

6 ^AoXB4G1E

1. save the result of psp service response
2. find the saved result
3-1. if payment success publish the event message to kafka cluster
3-2. if payment failed publish the event message to kafka cluster
4. receive the payment success event
5. find the saved psp result that processing in step.1
6. save the double-entry ledger data to relation database ^1JdjB5Ni

Payment-Service ^Dt8uV3ZB

Mysql ^BTc4swFA

payment.success ^za9p5H9V

payment.failure ^KMU7xajg

Kafka ^wGJfQ9Ab

Settlement-Service ^ZQRn8wyB

settlement.success ^w0osFMEv

scenario#2. ledger ^zY3wRcFy

1 ^tj4pX9jP

2 ^j8kWo1HQ

3-1 ^RAMgQ8Qb

3-2 ^oINhVBHG

4 ^ZX99KUzb

6 ^Bp1LPWp0

5 ^fs6YoqbQ

7 ^BaTwgiSW

8 ^yAsiC4sd

1...4 same as #2
5. find the ledger service...??
6. 
7. publish settlement complete message to kafka cluster
8. return the settlement completed message for customer or admin ^gZJGyCBk

checkout

1. payment_event save
2. payment_order save
 ^mEOF6VHO

confirm
1. update payment_event status to EXECUTING
2. update null fields
3. check amount is correct
4.  ^i0R6flDJ

Toss Payment ^Ow2EsAyh

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/1.9.19",
	"elements": [
		{
			"type": "rectangle",
			"version": 250,
			"versionNonce": 1426832919,
			"isDeleted": false,
			"id": "Tp1bLFz_qZG1-h5pfE8_s",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 202.6484375,
			"y": -124.3753875095407,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 165,
			"height": 71,
			"seed": 2000084128,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "q50YdR5t"
				},
				{
					"id": "ixLzlt5r5kK1Ofw98ZSSZ",
					"type": "arrow"
				},
				{
					"id": "CQaimObVsMIUE92iS2Hsj",
					"type": "arrow"
				},
				{
					"id": "Tx_BBUDFknYONZK6Ugpop",
					"type": "arrow"
				},
				{
					"id": "iq7IyIFWANvvK6mVrH5qQ",
					"type": "arrow"
				},
				{
					"id": "yT5q7LZuTe6Zrdq51bLbH",
					"type": "arrow"
				},
				{
					"id": "zf8U7u0wyR8MGWKb3Q8PC",
					"type": "arrow"
				},
				{
					"id": "C5k_0OssT5nA5MUqsWHR_",
					"type": "arrow"
				},
				{
					"id": "J50_vpqBL3os5yv0B00GU",
					"type": "arrow"
				},
				{
					"id": "K5wMUEJrXwOOK4S-iEahs",
					"type": "arrow"
				}
			],
			"updated": 1715428016422,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 158,
			"versionNonce": 556274393,
			"isDeleted": false,
			"id": "q50YdR5t",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 240.94847869873047,
			"y": -113.8753875095407,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 88.39991760253906,
			"height": 50,
			"seed": 2040140960,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016422,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Payment-\nService",
			"rawText": "Payment-Service",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "Tp1bLFz_qZG1-h5pfE8_s",
			"originalText": "Payment-Service",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "rectangle",
			"version": 582,
			"versionNonce": 1933173559,
			"isDeleted": false,
			"id": "zHH_q0pcqX06qRmyG8bG7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 204.79076796096615,
			"y": -391.216916464421,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 181,
			"height": 55,
			"seed": 870627488,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "Ow2EsAyh"
				},
				{
					"id": "yT5q7LZuTe6Zrdq51bLbH",
					"type": "arrow"
				},
				{
					"id": "zf8U7u0wyR8MGWKb3Q8PC",
					"type": "arrow"
				}
			],
			"updated": 1715428016422,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 549,
			"versionNonce": 1613909945,
			"isDeleted": false,
			"id": "Ow2EsAyh",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 225.76083021682552,
			"y": -376.216916464421,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 139.05987548828125,
			"height": 25,
			"seed": 1523820704,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016422,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Toss Payment",
			"rawText": "Toss Payment",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "zHH_q0pcqX06qRmyG8bG7",
			"originalText": "Toss Payment",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 306,
			"versionNonce": 782656599,
			"isDeleted": false,
			"id": "ixLzlt5r5kK1Ofw98ZSSZ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 324.8757165257868,
			"y": -45.86625188892535,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 249.87465416098047,
			"height": 187.60238711846185,
			"seed": 19129696,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016422,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Tp1bLFz_qZG1-h5pfE8_s",
				"gap": 7.509135620615339,
				"focus": 0.017188146999928225
			},
			"endBinding": {
				"elementId": "sGclqntWgB19lC6Dn8jx3",
				"gap": 10.429526947504883,
				"focus": -0.7625899596714188
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					109.7229162867132,
					113.06606133766569
				],
				[
					249.87465416098047,
					187.60238711846185
				]
			]
		},
		{
			"type": "arrow",
			"version": 202,
			"versionNonce": 1084354713,
			"isDeleted": false,
			"id": "CQaimObVsMIUE92iS2Hsj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 332.2531509382625,
			"y": -45.5853484470407,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 244.42559291485998,
			"height": 125.31359291308858,
			"seed": 160381280,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016422,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Tp1bLFz_qZG1-h5pfE8_s",
				"gap": 7.7900390625,
				"focus": 0.31937093409921813
			},
			"endBinding": {
				"elementId": "tFfGI8hrdX7ZJZxGceZNY",
				"gap": 7.325372531149696,
				"focus": -0.7811844717652181
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					134.96071624923752,
					58.7086394626657
				],
				[
					244.42559291485998,
					125.31359291308858
				]
			]
		},
		{
			"type": "rectangle",
			"version": 321,
			"versionNonce": 119914871,
			"isDeleted": false,
			"id": "1wf2U9GNeo_OCwBk63ZWE",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1017.1718659788432,
			"y": -138.53927893250824,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 230,
			"height": 62,
			"seed": 2061457760,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "JVTxdaTg"
				},
				{
					"id": "qW1qaMHo4QsWD4EsL_5Oe",
					"type": "arrow"
				},
				{
					"id": "pasqZRXx_p6uSDuNEANkV",
					"type": "arrow"
				},
				{
					"id": "DECaDL4D7ETY8rgxoFUsG",
					"type": "arrow"
				}
			],
			"updated": 1715428016422,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 298,
			"versionNonce": 942306681,
			"isDeleted": false,
			"id": "JVTxdaTg",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1062.3719392210307,
			"y": -120.03927893250824,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 139.599853515625,
			"height": 25,
			"seed": 488900960,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016422,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Ledger-Service",
			"rawText": "Ledger-Service",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "1wf2U9GNeo_OCwBk63ZWE",
			"originalText": "Ledger-Service",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 640,
			"versionNonce": 234650263,
			"isDeleted": false,
			"id": "qW1qaMHo4QsWD4EsL_5Oe",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 829.4579440816259,
			"y": 85.66570017557808,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 181.17117129379028,
			"height": 157.9141673026791,
			"seed": 288194720,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016422,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "tFfGI8hrdX7ZJZxGceZNY",
				"gap": 12.453827697353745,
				"focus": 0.964959988371381
			},
			"endBinding": {
				"elementId": "1wf2U9GNeo_OCwBk63ZWE",
				"gap": 7.824234876846958,
				"focus": 0.42611843986220527
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					82.35702771422086,
					-91.84591237382165
				],
				[
					181.17117129379028,
					-157.9141673026791
				]
			]
		},
		{
			"type": "line",
			"version": 4847,
			"versionNonce": 974085721,
			"isDeleted": false,
			"id": "8S40H1j_nDBSzLLwOR5Y7",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 660.5061498393584,
			"y": -225.37377227815597,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 77.09201683999922,
			"height": 99.49948667804088,
			"seed": 717486432,
			"groupIds": [
				"lAm0l0ujvvuvOF_4eAHz9",
				"ynf2S56aG_dVfbmI8pXP4"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016422,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.2542098813493443,
					75.20117273657175
				],
				[
					0.011896425679918422,
					83.76249969444815
				],
				[
					3.970409367559332,
					87.46174320643391
				],
				[
					17.75573317066317,
					90.59250103325854
				],
				[
					41.05683533152865,
					91.56737225214069
				],
				[
					63.319497586673116,
					90.01084754868091
				],
				[
					75.14781395923075,
					86.28844687220405
				],
				[
					76.81603792670788,
					83.15042405259751
				],
				[
					77.05033394391478,
					76.25776215104557
				],
				[
					76.86643881413028,
					6.3089586511537865
				],
				[
					76.45188016352971,
					-0.2999144698665015
				],
				[
					71.50179495549581,
					-3.9936571317850627
				],
				[
					61.077971898861186,
					-6.132877429442784
				],
				[
					37.32348754161154,
					-7.932114425900202
				],
				[
					18.278415656797975,
					-6.859225353587373
				],
				[
					3.2995959613238286,
					-3.2201165291205287
				],
				[
					-0.04168289608444441,
					-0.045185660461322996
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 2552,
			"versionNonce": 937365431,
			"isDeleted": false,
			"id": "STFMNcB0zkoJ0uoGwHoZv",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 661.0300792776334,
			"y": -168.24748862042605,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 77.17198221193564,
			"height": 8.562348957853038,
			"seed": 381537632,
			"groupIds": [
				"lAm0l0ujvvuvOF_4eAHz9",
				"ynf2S56aG_dVfbmI8pXP4"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016422,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.033150371639873,
					3.413095389435587
				],
				[
					10.801287372573954,
					6.276651055277943
				],
				[
					22.468666942209353,
					8.010803051612635
				],
				[
					40.747074201802775,
					8.168828515515864
				],
				[
					62.077348233027564,
					7.0647721921469495
				],
				[
					74.53446931782398,
					3.04824021069218
				],
				[
					77.17198221193564,
					-0.3935204423371723
				]
			]
		},
		{
			"type": "line",
			"version": 2638,
			"versionNonce": 86256441,
			"isDeleted": false,
			"id": "WRbuG1DU2wcDDMsdzqg_6",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 659.9982219551296,
			"y": -197.2115439556491,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 77.17198221193564,
			"height": 8.562348957853038,
			"seed": 207429984,
			"groupIds": [
				"lAm0l0ujvvuvOF_4eAHz9",
				"ynf2S56aG_dVfbmI8pXP4"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016422,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.033150371639873,
					3.413095389435587
				],
				[
					10.801287372573954,
					6.276651055277943
				],
				[
					22.468666942209353,
					8.010803051612635
				],
				[
					40.747074201802775,
					8.168828515515864
				],
				[
					62.077348233027564,
					7.0647721921469495
				],
				[
					74.53446931782398,
					3.04824021069218
				],
				[
					77.17198221193564,
					-0.3935204423371723
				]
			]
		},
		{
			"type": "ellipse",
			"version": 5635,
			"versionNonce": 1861353687,
			"isDeleted": false,
			"id": "IHNpCeAJsBFoSsslNcthu",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 658.9402729730475,
			"y": -232.5060409038376,
			"strokeColor": "#000000",
			"backgroundColor": "#fff",
			"width": 76.59753601865496,
			"height": 15.49127539284798,
			"seed": 988935520,
			"groupIds": [
				"lAm0l0ujvvuvOF_4eAHz9",
				"ynf2S56aG_dVfbmI8pXP4"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016422,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1039,
			"versionNonce": 835476505,
			"isDeleted": false,
			"id": "bPUMkvRncurrfHiAfeBS-",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 695.4322600782699,
			"y": -208.02937322393393,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 11.226103154161754,
			"height": 12.183758484455605,
			"seed": 1741441376,
			"groupIds": [
				"lAm0l0ujvvuvOF_4eAHz9",
				"ynf2S56aG_dVfbmI8pXP4"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016422,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1327,
			"versionNonce": 1690947063,
			"isDeleted": false,
			"id": "uPG_AoUCkYYKuYrfkyl9U",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 695.7834018622035,
			"y": -181.81275893686885,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 11.226103154161754,
			"height": 12.183758484455605,
			"seed": 775691616,
			"groupIds": [
				"lAm0l0ujvvuvOF_4eAHz9",
				"ynf2S56aG_dVfbmI8pXP4"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016422,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1210,
			"versionNonce": 2147184889,
			"isDeleted": false,
			"id": "ntnKp2jWfiExC-98r0iVm",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.239590202363168,
			"x": 696.4322600782699,
			"y": -153.04403236556246,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 11.226103154161754,
			"height": 12.183758484455605,
			"seed": 1066496352,
			"groupIds": [
				"lAm0l0ujvvuvOF_4eAHz9",
				"ynf2S56aG_dVfbmI8pXP4"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016422,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 708,
			"versionNonce": 610989847,
			"isDeleted": false,
			"id": "RHsr4Tlc",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 676.0582184902163,
			"y": -131.45389076671964,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 45.19486999511719,
			"height": 23.595161071904883,
			"seed": 589055328,
			"groupIds": [
				"ynf2S56aG_dVfbmI8pXP4"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Tx_BBUDFknYONZK6Ugpop",
					"type": "arrow"
				},
				{
					"id": "iq7IyIFWANvvK6mVrH5qQ",
					"type": "arrow"
				},
				{
					"id": "pasqZRXx_p6uSDuNEANkV",
					"type": "arrow"
				},
				{
					"id": "DECaDL4D7ETY8rgxoFUsG",
					"type": "arrow"
				},
				{
					"id": "W0D9_70XOi5NjhoC2zVU2",
					"type": "arrow"
				},
				{
					"id": "4di3vNqF_gWFxnDVB6bz9",
					"type": "arrow"
				}
			],
			"updated": 1715428016422,
			"link": null,
			"locked": false,
			"fontSize": 17.4778970902999,
			"fontFamily": 1,
			"text": "Mysql",
			"rawText": "Mysql",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Mysql",
			"lineHeight": 1.350000000000001,
			"baseline": 15
		},
		{
			"type": "arrow",
			"version": 389,
			"versionNonce": 1697966553,
			"isDeleted": false,
			"id": "Tx_BBUDFknYONZK6Ugpop",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 377.9880585044697,
			"y": -105.53105480168392,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 286.9836287866166,
			"height": 20.456421196807696,
			"seed": 2147034464,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016422,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Tp1bLFz_qZG1-h5pfE8_s",
				"gap": 10.339621004469677,
				"focus": -0.07236957305960698
			},
			"endBinding": {
				"elementId": "RHsr4Tlc",
				"focus": 0.40084271958315,
				"gap": 11.086531199130036
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					143.4916009081312,
					-20.456421196807696
				],
				[
					286.9836287866166,
					-19.221943638932714
				]
			]
		},
		{
			"type": "arrow",
			"version": 284,
			"versionNonce": 1682570295,
			"isDeleted": false,
			"id": "iq7IyIFWANvvK6mVrH5qQ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 664.8539147632124,
			"y": -102.89541646687411,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 287.2356888838436,
			"height": 21.00183599111773,
			"seed": 2088752288,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016422,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "RHsr4Tlc",
				"focus": -0.7727086083083872,
				"gap": 11.20430372700389
			},
			"endBinding": {
				"elementId": "Tp1bLFz_qZG1-h5pfE8_s",
				"gap": 9.969788379368822,
				"focus": 0.14218539647612596
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-140.82988069538806,
					21.00183599111773
				],
				[
					-287.2356888838436,
					19.871847228610292
				]
			]
		},
		{
			"type": "arrow",
			"version": 136,
			"versionNonce": 1519142585,
			"isDeleted": false,
			"id": "yT5q7LZuTe6Zrdq51bLbH",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 264.57362334483906,
			"y": -134.71329886254682,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 4.672872349514648,
			"height": 194.51707567380447,
			"seed": 767321248,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Tp1bLFz_qZG1-h5pfE8_s",
				"gap": 10.33791135300612,
				"focus": -0.2600509145587543
			},
			"endBinding": {
				"elementId": "zHH_q0pcqX06qRmyG8bG7",
				"gap": 6.986541928069698,
				"focus": 0.2766084858838066
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					4.672872349514648,
					-194.51707567380447
				]
			]
		},
		{
			"type": "arrow",
			"version": 195,
			"versionNonce": 407592279,
			"isDeleted": false,
			"id": "zf8U7u0wyR8MGWKb3Q8PC",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 299.5079089571915,
			"y": -327.41365286918904,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 5.687902812026323,
			"height": 196.9793823619761,
			"seed": 493437280,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "zHH_q0pcqX06qRmyG8bG7",
				"gap": 8.803263595231954,
				"focus": -0.05767537660854322
			},
			"endBinding": {
				"elementId": "Tp1bLFz_qZG1-h5pfE8_s",
				"gap": 6.058882997672242,
				"focus": 0.08945252727956182
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-5.687902812026323,
					196.9793823619761
				]
			]
		},
		{
			"type": "arrow",
			"version": 221,
			"versionNonce": 1789200281,
			"isDeleted": false,
			"id": "pasqZRXx_p6uSDuNEANkV",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 729.6534669337298,
			"y": -129.86687289997258,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 282.98091639668155,
			"height": 22.976096253299886,
			"seed": 703020384,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "RHsr4Tlc",
				"focus": -0.5928570319311917,
				"gap": 8.400378448396282
			},
			"endBinding": {
				"elementId": "1wf2U9GNeo_OCwBk63ZWE",
				"gap": 4.537482648431933,
				"focus": -0.1969837094290484
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					140.86045912293787,
					-10.20494796420789
				],
				[
					282.98091639668155,
					12.771148289091997
				]
			]
		},
		{
			"type": "arrow",
			"version": 241,
			"versionNonce": 1136892535,
			"isDeleted": false,
			"id": "DECaDL4D7ETY8rgxoFUsG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1009.3350870170113,
			"y": -99.07337879219361,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 285.017146270327,
			"height": 18.25437353578613,
			"seed": 1663892832,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "1wf2U9GNeo_OCwBk63ZWE",
				"gap": 7.836778961831897,
				"focus": -0.10358555737575575
			},
			"endBinding": {
				"elementId": "RHsr4Tlc",
				"focus": 0.31289495607806467,
				"gap": 3.064852261350893
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-142.33872960811811,
					5.550716366894932
				],
				[
					-285.017146270327,
					-12.703657168891198
				]
			]
		},
		{
			"type": "rectangle",
			"version": 546,
			"versionNonce": 2142415993,
			"isDeleted": false,
			"id": "tFfGI8hrdX7ZJZxGceZNY",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 584.0041163842722,
			"y": 56.94786752156699,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 233,
			"height": 48,
			"seed": 1079705760,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "myPYhfXq"
				},
				{
					"id": "CQaimObVsMIUE92iS2Hsj",
					"type": "arrow"
				},
				{
					"id": "qW1qaMHo4QsWD4EsL_5Oe",
					"type": "arrow"
				},
				{
					"id": "t4RzpCsllEN-3UJepog5j",
					"type": "arrow"
				}
			],
			"updated": 1715428016423,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 390,
			"versionNonce": 192361367,
			"isDeleted": false,
			"id": "myPYhfXq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 621.8741954247995,
			"y": 68.44786752156699,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 157.2598419189453,
			"height": 25,
			"seed": 1248980128,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "payment.success",
			"rawText": "payment.success",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "tFfGI8hrdX7ZJZxGceZNY",
			"originalText": "payment.success",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 619,
			"versionNonce": 1903736153,
			"isDeleted": false,
			"id": "sGclqntWgB19lC6Dn8jx3",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 585.1798976342722,
			"y": 119.69005337578585,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 233,
			"height": 48,
			"seed": 1254840480,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "dWkDPNPO"
				},
				{
					"id": "ixLzlt5r5kK1Ofw98ZSSZ",
					"type": "arrow"
				}
			],
			"updated": 1715428016423,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 477,
			"versionNonce": 127576247,
			"isDeleted": false,
			"id": "dWkDPNPO",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 628.7299693505807,
			"y": 131.19005337578585,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 145.8998565673828,
			"height": 25,
			"seed": 1427588256,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "payment.failure",
			"rawText": "payment.failure",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "sGclqntWgB19lC6Dn8jx3",
			"originalText": "payment.failure",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 192,
			"versionNonce": 1397400121,
			"isDeleted": false,
			"id": "T5CvAf4u5j1nwP6KkUm_K",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 539.3096984026413,
			"y": 5.7828333258655675,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 314.3771962107555,
			"height": 246.64586856693924,
			"seed": 255969440,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 76,
			"versionNonce": 1439857111,
			"isDeleted": false,
			"id": "v6iMerNv",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 555.9846079905233,
			"y": 13.659619411347535,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 58.39996337890625,
			"height": 25,
			"seed": 239116448,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Kafka",
			"rawText": "Kafka",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Kafka",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 508,
			"versionNonce": 34337561,
			"isDeleted": false,
			"id": "GXriyovim_e6ETyIsRsEH",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1018.0556568675959,
			"y": 27.943365916391826,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 230,
			"height": 62,
			"seed": 54064288,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "8i0gw7h8"
				},
				{
					"id": "t4RzpCsllEN-3UJepog5j",
					"type": "arrow"
				},
				{
					"id": "sRZszLizLa3P1W53_HYy7",
					"type": "arrow"
				},
				{
					"id": "W0D9_70XOi5NjhoC2zVU2",
					"type": "arrow"
				},
				{
					"id": "4di3vNqF_gWFxnDVB6bz9",
					"type": "arrow"
				}
			],
			"updated": 1715428016423,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 492,
			"versionNonce": 1798514423,
			"isDeleted": false,
			"id": "8i0gw7h8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1042.1157536083185,
			"y": 46.443365916391826,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 181.8798065185547,
			"height": 25,
			"seed": 1701929120,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Settlement-Service",
			"rawText": "Settlement-Service",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "GXriyovim_e6ETyIsRsEH",
			"originalText": "Settlement-Service",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 593,
			"versionNonce": 1915758585,
			"isDeleted": false,
			"id": "Gg5RjUEcJVY4yPAmVtFcb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 586.5731070570397,
			"y": 179.2689813571866,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 233,
			"height": 48,
			"seed": 919872864,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "ezwmArHN"
				},
				{
					"id": "sRZszLizLa3P1W53_HYy7",
					"type": "arrow"
				},
				{
					"id": "C5k_0OssT5nA5MUqsWHR_",
					"type": "arrow"
				}
			],
			"updated": 1715428016423,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 455,
			"versionNonce": 641806359,
			"isDeleted": false,
			"id": "ezwmArHN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 610.4332068495202,
			"y": 190.7689813571866,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 185.27980041503906,
			"height": 25,
			"seed": 132675936,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "settlement.success",
			"rawText": "settlement.success",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "Gg5RjUEcJVY4yPAmVtFcb",
			"originalText": "settlement.success",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 706,
			"versionNonce": 1035649241,
			"isDeleted": false,
			"id": "t4RzpCsllEN-3UJepog5j",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 829.7347067551439,
			"y": 95.7268130145086,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 182.1755467901353,
			"height": 32.51438619123706,
			"seed": 293952864,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "tFfGI8hrdX7ZJZxGceZNY",
				"gap": 12.73059037087171,
				"focus": 0.7934212133031727
			},
			"endBinding": {
				"elementId": "GXriyovim_e6ETyIsRsEH",
				"gap": 6.145403322316724,
				"focus": 0.44960487660753723
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					104.21621514303547,
					-12.074097019050896
				],
				[
					182.1755467901353,
					-32.51438619123706
				]
			]
		},
		{
			"type": "arrow",
			"version": 394,
			"versionNonce": 552670519,
			"isDeleted": false,
			"id": "sRZszLizLa3P1W53_HYy7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1010.0947293862041,
			"y": 87.48423671233772,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 182.98203294497262,
			"height": 123.82274231015901,
			"seed": 1458172064,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "GXriyovim_e6ETyIsRsEH",
				"gap": 7.960927481391764,
				"focus": 0.6059555037372533
			},
			"endBinding": {
				"elementId": "Gg5RjUEcJVY4yPAmVtFcb",
				"gap": 7.5395893841918,
				"focus": 0.8599967447294963
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-75.3995487722151,
					66.97795844090015
				],
				[
					-182.98203294497262,
					123.82274231015901
				]
			]
		},
		{
			"type": "arrow",
			"version": 203,
			"versionNonce": 1916747193,
			"isDeleted": false,
			"id": "C5k_0OssT5nA5MUqsWHR_",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 579.8188367431748,
			"y": 207.739365847199,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 301.45318686667656,
			"height": 256.22891602649315,
			"seed": 293043360,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Gg5RjUEcJVY4yPAmVtFcb",
				"gap": 6.754270313864936,
				"focus": -0.8272176127787945
			},
			"endBinding": {
				"elementId": "Tp1bLFz_qZG1-h5pfE8_s",
				"gap": 4.885837330246545,
				"focus": 0.3541358933227096
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-176.03295114437992,
					-100.72701192370255
				],
				[
					-301.45318686667656,
					-256.22891602649315
				]
			]
		},
		{
			"type": "text",
			"version": 315,
			"versionNonce": 1118262871,
			"isDeleted": false,
			"id": "DOZVqIbm",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -72.48799094235756,
			"y": -104.24124354130487,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 96.16270446777344,
			"height": 44.449430618532524,
			"seed": 1987505504,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "J50_vpqBL3os5yv0B00GU",
					"type": "arrow"
				},
				{
					"id": "K5wMUEJrXwOOK4S-iEahs",
					"type": "arrow"
				}
			],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"fontSize": 35.55954449482602,
			"fontFamily": 1,
			"text": "Client",
			"rawText": "Client",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Client",
			"lineHeight": 1.25,
			"baseline": 31
		},
		{
			"type": "arrow",
			"version": 428,
			"versionNonce": 518069913,
			"isDeleted": false,
			"id": "J50_vpqBL3os5yv0B00GU",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 32.71341179967935,
			"y": -92.42016355015204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 165.79715444063896,
			"height": 6.899207503004035,
			"seed": 670282080,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "DOZVqIbm",
				"gap": 9.038698274263481,
				"focus": -0.3313211017908013
			},
			"endBinding": {
				"elementId": "Tp1bLFz_qZG1-h5pfE8_s",
				"gap": 4.137871259681674,
				"focus": 0.36085535576006667
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					165.79715444063896,
					-6.899207503004035
				]
			]
		},
		{
			"type": "arrow",
			"version": 448,
			"versionNonce": 305689463,
			"isDeleted": false,
			"id": "K5wMUEJrXwOOK4S-iEahs",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 195.67118733139364,
			"y": -70.25617124828501,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 166.1911352461836,
			"height": 2.511649968541164,
			"seed": 106798240,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Tp1bLFz_qZG1-h5pfE8_s",
				"gap": 6.977250168606361,
				"focus": -0.5434959836931347
			},
			"endBinding": {
				"elementId": "DOZVqIbm",
				"gap": 5.805338559794166,
				"focus": 0.3674864055946698
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-166.1911352461836,
					-2.511649968541164
				]
			]
		},
		{
			"type": "arrow",
			"version": 315,
			"versionNonce": 575923065,
			"isDeleted": false,
			"id": "W0D9_70XOi5NjhoC2zVU2",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 703.4823703948342,
			"y": -96.14170458962656,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 311.28718133451605,
			"height": 131.82139000379595,
			"seed": 1551202656,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "RHsr4Tlc",
				"focus": 0.8622002830926077,
				"gap": 11.717025105188192
			},
			"endBinding": {
				"elementId": "GXriyovim_e6ETyIsRsEH",
				"gap": 3.2861051382456026,
				"focus": -0.20602109605320895
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					145.4892649847045,
					79.85212817764386
				],
				[
					311.28718133451605,
					131.82139000379595
				]
			]
		},
		{
			"type": "arrow",
			"version": 428,
			"versionNonce": 1206447255,
			"isDeleted": false,
			"id": "4di3vNqF_gWFxnDVB6bz9",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1023.2106432587211,
			"y": 21.344750966960532,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 311.997528516118,
			"height": 125.26399086818986,
			"seed": 912879776,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "GXriyovim_e6ETyIsRsEH",
				"gap": 6.598614949431294,
				"focus": -0.1759570954283953
			},
			"endBinding": {
				"elementId": "RHsr4Tlc",
				"focus": 0.6001674623406246,
				"gap": 3.939489793585416
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-146.69370013309447,
					-70.47929200616204
				],
				[
					-311.997528516118,
					-125.26399086818986
				]
			]
		},
		{
			"type": "text",
			"version": 97,
			"versionNonce": 953879641,
			"isDeleted": false,
			"id": "BRt7vuQs",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1713.6324064378502,
			"y": -407.7820333722133,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 192.23983764648438,
			"height": 25,
			"seed": 1905891630,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "scenario#1. payment",
			"rawText": "scenario#1. payment",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "scenario#1. payment",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 360,
			"versionNonce": 527253943,
			"isDeleted": false,
			"id": "ZZdEuOwk942KDmHCRYNg9",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2134.6157525269396,
			"y": -86.7244110324591,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 165,
			"height": 71,
			"seed": 1441966510,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "Hl6VxnD3"
				},
				{
					"id": "rOu9GlJhIkHXX3zLvwKl1",
					"type": "arrow"
				},
				{
					"id": "KEq8oMQCesjlgHxHNxplh",
					"type": "arrow"
				},
				{
					"id": "SOk00HXHXd-FGhuPw97vp",
					"type": "arrow"
				},
				{
					"id": "yEHDV-EmnusK9YsDUNNhM",
					"type": "arrow"
				},
				{
					"id": "HcJ7NbPdh2xbPyinE8Agq",
					"type": "arrow"
				},
				{
					"id": "FrivM8gHegnbQl-uQxgfQ",
					"type": "arrow"
				}
			],
			"updated": 1715428016423,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 266,
			"versionNonce": 1246370105,
			"isDeleted": false,
			"id": "Hl6VxnD3",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2172.91579372567,
			"y": -76.2244110324591,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 88.39991760253906,
			"height": 50,
			"seed": 428688366,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Payment-\nService",
			"rawText": "Payment-Service",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "ZZdEuOwk942KDmHCRYNg9",
			"originalText": "Payment-Service",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "rectangle",
			"version": 688,
			"versionNonce": 1776939735,
			"isDeleted": false,
			"id": "evQD59gVGLwW8tr_X5_5t",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2136.7580829879057,
			"y": -353.5659399873394,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 181,
			"height": 55,
			"seed": 995792430,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "2yDPvFHo"
				},
				{
					"id": "SOk00HXHXd-FGhuPw97vp",
					"type": "arrow"
				},
				{
					"id": "yEHDV-EmnusK9YsDUNNhM",
					"type": "arrow"
				}
			],
			"updated": 1715428016423,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 656,
			"versionNonce": 2013563417,
			"isDeleted": false,
			"id": "2yDPvFHo",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2157.728145243765,
			"y": -338.5659399873394,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 139.05987548828125,
			"height": 25,
			"seed": 1413718126,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Toss Payment",
			"rawText": "Toss Payment",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "evQD59gVGLwW8tr_X5_5t",
			"originalText": "Toss Payment",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "line",
			"version": 4955,
			"versionNonce": 1609793527,
			"isDeleted": false,
			"id": "qvAtVNpWXIxLECZWJC8JF",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2592.473464866298,
			"y": -187.72279580107437,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 77.09201683999922,
			"height": 99.49948667804088,
			"seed": 1412953582,
			"groupIds": [
				"6Sn-TnWcL5nLRvaTkW3_x",
				"hfH7JGqmws9SGci5VPNaF"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.2542098813493443,
					75.20117273657175
				],
				[
					0.011896425679918422,
					83.76249969444815
				],
				[
					3.970409367559332,
					87.46174320643391
				],
				[
					17.75573317066317,
					90.59250103325854
				],
				[
					41.05683533152865,
					91.56737225214069
				],
				[
					63.319497586673116,
					90.01084754868091
				],
				[
					75.14781395923075,
					86.28844687220405
				],
				[
					76.81603792670788,
					83.15042405259751
				],
				[
					77.05033394391478,
					76.25776215104557
				],
				[
					76.86643881413028,
					6.3089586511537865
				],
				[
					76.45188016352971,
					-0.2999144698665015
				],
				[
					71.50179495549581,
					-3.9936571317850627
				],
				[
					61.077971898861186,
					-6.132877429442784
				],
				[
					37.32348754161154,
					-7.932114425900202
				],
				[
					18.278415656797975,
					-6.859225353587373
				],
				[
					3.2995959613238286,
					-3.2201165291205287
				],
				[
					-0.04168289608444441,
					-0.045185660461322996
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 2660,
			"versionNonce": 1795022585,
			"isDeleted": false,
			"id": "C2gNQ0eZ1gMaIMtXYqI0E",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2592.997394304573,
			"y": -130.59651214334446,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 77.17198221193564,
			"height": 8.562348957853038,
			"seed": 1910442030,
			"groupIds": [
				"6Sn-TnWcL5nLRvaTkW3_x",
				"hfH7JGqmws9SGci5VPNaF"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.033150371639873,
					3.413095389435587
				],
				[
					10.801287372573954,
					6.276651055277943
				],
				[
					22.468666942209353,
					8.010803051612635
				],
				[
					40.747074201802775,
					8.168828515515864
				],
				[
					62.077348233027564,
					7.0647721921469495
				],
				[
					74.53446931782398,
					3.04824021069218
				],
				[
					77.17198221193564,
					-0.3935204423371723
				]
			]
		},
		{
			"type": "line",
			"version": 2746,
			"versionNonce": 864971031,
			"isDeleted": false,
			"id": "0qkTDhngH463nqc4gTYaN",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2591.9655369820694,
			"y": -159.5605674785675,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 77.17198221193564,
			"height": 8.562348957853038,
			"seed": 1701433966,
			"groupIds": [
				"6Sn-TnWcL5nLRvaTkW3_x",
				"hfH7JGqmws9SGci5VPNaF"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.033150371639873,
					3.413095389435587
				],
				[
					10.801287372573954,
					6.276651055277943
				],
				[
					22.468666942209353,
					8.010803051612635
				],
				[
					40.747074201802775,
					8.168828515515864
				],
				[
					62.077348233027564,
					7.0647721921469495
				],
				[
					74.53446931782398,
					3.04824021069218
				],
				[
					77.17198221193564,
					-0.3935204423371723
				]
			]
		},
		{
			"type": "ellipse",
			"version": 5743,
			"versionNonce": 1639552985,
			"isDeleted": false,
			"id": "V9wyFgfCjGKQBYWswzdGd",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2590.9075879999873,
			"y": -194.855064426756,
			"strokeColor": "#000000",
			"backgroundColor": "#fff",
			"width": 76.59753601865496,
			"height": 15.49127539284798,
			"seed": 698438830,
			"groupIds": [
				"6Sn-TnWcL5nLRvaTkW3_x",
				"hfH7JGqmws9SGci5VPNaF"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1147,
			"versionNonce": 1647259191,
			"isDeleted": false,
			"id": "8A6Pnj2SL8liRtzrWn40Y",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2627.3995751052094,
			"y": -170.37839674685233,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 11.226103154161754,
			"height": 12.183758484455605,
			"seed": 2016317166,
			"groupIds": [
				"6Sn-TnWcL5nLRvaTkW3_x",
				"hfH7JGqmws9SGci5VPNaF"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1435,
			"versionNonce": 2118857913,
			"isDeleted": false,
			"id": "6kMNeWag5594HxShZvoH1",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2627.750716889143,
			"y": -144.16178245978725,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 11.226103154161754,
			"height": 12.183758484455605,
			"seed": 1838842158,
			"groupIds": [
				"6Sn-TnWcL5nLRvaTkW3_x",
				"hfH7JGqmws9SGci5VPNaF"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1318,
			"versionNonce": 1186615127,
			"isDeleted": false,
			"id": "I357_cQ8CMIpc3HJBZOrp",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.239590202363168,
			"x": 2628.3995751052094,
			"y": -115.39305588848086,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 11.226103154161754,
			"height": 12.183758484455605,
			"seed": 760097646,
			"groupIds": [
				"6Sn-TnWcL5nLRvaTkW3_x",
				"hfH7JGqmws9SGci5VPNaF"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 820,
			"versionNonce": 1414935961,
			"isDeleted": false,
			"id": "doYTOaXY",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2608.025533517156,
			"y": -93.80291428963804,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 45.19486999511719,
			"height": 23.595161071904883,
			"seed": 93490606,
			"groupIds": [
				"hfH7JGqmws9SGci5VPNaF"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "rOu9GlJhIkHXX3zLvwKl1",
					"type": "arrow"
				},
				{
					"id": "KEq8oMQCesjlgHxHNxplh",
					"type": "arrow"
				}
			],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"fontSize": 17.4778970902999,
			"fontFamily": 1,
			"text": "Mysql",
			"rawText": "Mysql",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Mysql",
			"lineHeight": 1.350000000000001,
			"baseline": 15
		},
		{
			"type": "arrow",
			"version": 704,
			"versionNonce": 1803832439,
			"isDeleted": false,
			"id": "rOu9GlJhIkHXX3zLvwKl1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2309.955373531409,
			"y": -67.88007679476982,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 286.9836287866169,
			"height": 19.22194506352048,
			"seed": 328247278,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "lf5QFqSD"
				}
			],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ZZdEuOwk942KDmHCRYNg9",
				"gap": 10.339621004469336,
				"focus": -0.25440922174830416
			},
			"endBinding": {
				"elementId": "doYTOaXY",
				"gap": 11.08653119913015,
				"focus": 0.5523805461979192
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					286.9836287866169,
					-19.22194506352048
				]
			]
		},
		{
			"type": "text",
			"version": 8,
			"versionNonce": 923671161,
			"isDeleted": false,
			"id": "lf5QFqSD",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2447.047194028233,
			"y": -89.99104932653006,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 12.79998779296875,
			"height": 25,
			"seed": 865357678,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "4",
			"rawText": "4",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "rOu9GlJhIkHXX3zLvwKl1",
			"originalText": "4",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 595,
			"versionNonce": 475112855,
			"isDeleted": false,
			"id": "KEq8oMQCesjlgHxHNxplh",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2597.8404628239073,
			"y": -65.53866749170945,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 288.25492191759895,
			"height": 19.94232757796199,
			"seed": 1733392942,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "RblQKStJ"
				}
			],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "doYTOaXY",
				"gap": 11.204286079149824,
				"focus": -1.0627005179981046
			},
			"endBinding": {
				"elementId": "ZZdEuOwk942KDmHCRYNg9",
				"gap": 9.969788379368765,
				"focus": 0.2918249596661703
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-288.25492191759895,
					19.94232757796199
				]
			]
		},
		{
			"type": "text",
			"version": 8,
			"versionNonce": 1194746713,
			"isDeleted": false,
			"id": "RblQKStJ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2447.023401496376,
			"y": -68.03224753613304,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 12.3599853515625,
			"height": 25,
			"seed": 145364082,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "5",
			"rawText": "5",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "KEq8oMQCesjlgHxHNxplh",
			"originalText": "5",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 466,
			"versionNonce": 945216183,
			"isDeleted": false,
			"id": "SOk00HXHXd-FGhuPw97vp",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2196.5409383718825,
			"y": -97.06232238546522,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 4.672872349429326,
			"height": 194.51707567380447,
			"seed": 666764398,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "6Sl0SAL9"
				}
			],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ZZdEuOwk942KDmHCRYNg9",
				"gap": 10.33791135300612,
				"focus": -0.2600509145573157
			},
			"endBinding": {
				"elementId": "evQD59gVGLwW8tr_X5_5t",
				"gap": 6.986541928069698,
				"focus": 0.27660848588380577
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					4.672872349429326,
					-194.51707567380447
				]
			]
		},
		{
			"type": "text",
			"version": 8,
			"versionNonce": 1092784185,
			"isDeleted": false,
			"id": "6Sl0SAL9",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2191.7573794294094,
			"y": -206.82086022236746,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 14.239990234375,
			"height": 25,
			"seed": 1338574510,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "2",
			"rawText": "2",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "SOk00HXHXd-FGhuPw97vp",
			"originalText": "2",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 525,
			"versionNonce": 1144548311,
			"isDeleted": false,
			"id": "yEHDV-EmnusK9YsDUNNhM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2231.475223984733,
			"y": -289.76267639210744,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 5.687902812516768,
			"height": 196.9793823619761,
			"seed": 916407982,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "eFpxFj3m"
				}
			],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "evQD59gVGLwW8tr_X5_5t",
				"gap": 8.803263595231954,
				"focus": -0.057675376616083594
			},
			"endBinding": {
				"elementId": "ZZdEuOwk942KDmHCRYNg9",
				"gap": 6.058882997672242,
				"focus": 0.08945252727956322
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-5.687902812516768,
					196.9793823619761
				]
			]
		},
		{
			"type": "text",
			"version": 8,
			"versionNonce": 179708185,
			"isDeleted": false,
			"id": "eFpxFj3m",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2221.821275019881,
			"y": -203.7729852111194,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 13.6199951171875,
			"height": 25,
			"seed": 1568687090,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "3",
			"rawText": "3",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "yEHDV-EmnusK9YsDUNNhM",
			"originalText": "3",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 453,
			"versionNonce": 1007343863,
			"isDeleted": false,
			"id": "zrprptru",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1802.3024350425717,
			"y": -73.11838983054997,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 97.43403625488281,
			"height": 45.030322388650994,
			"seed": 719661742,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "HcJ7NbPdh2xbPyinE8Agq",
					"type": "arrow"
				},
				{
					"id": "FrivM8gHegnbQl-uQxgfQ",
					"type": "arrow"
				}
			],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"fontSize": 36.024257910920795,
			"fontFamily": 1,
			"text": "Client",
			"rawText": "Client",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Client",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "arrow",
			"version": 801,
			"versionNonce": 23369209,
			"isDeleted": false,
			"id": "HcJ7NbPdh2xbPyinE8Agq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1908.7751695717182,
			"y": -59.31442934387578,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 221.70271169553985,
			"height": 3.7567348573296115,
			"seed": 243770606,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "Lu2MJRvo"
				}
			],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "zrprptru",
				"gap": 9.038698274263652,
				"focus": -0.33132110179080076
			},
			"endBinding": {
				"elementId": "ZZdEuOwk942KDmHCRYNg9",
				"gap": 4.13787125968156,
				"focus": 0.36085535576006755
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					221.70271169553985,
					-3.7567348573296115
				]
			]
		},
		{
			"type": "text",
			"version": 8,
			"versionNonce": 626172439,
			"isDeleted": false,
			"id": "Lu2MJRvo",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2015.7209647947377,
			"y": -75.63685900706542,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 5.4199981689453125,
			"height": 25,
			"seed": 1043214514,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1",
			"rawText": "1",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "HcJ7NbPdh2xbPyinE8Agq",
			"originalText": "1",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 821,
			"versionNonce": 137457369,
			"isDeleted": false,
			"id": "FrivM8gHegnbQl-uQxgfQ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2127.6385023583334,
			"y": -33.2972701850876,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 222.0966925010846,
			"height": 6.81091858321895,
			"seed": 1147197230,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "XoO3Mk0l"
				}
			],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ZZdEuOwk942KDmHCRYNg9",
				"gap": 6.977250168606133,
				"focus": -0.5435008915931252
			},
			"endBinding": {
				"elementId": "zrprptru",
				"gap": 5.805338559794336,
				"focus": 0.36748640559467094
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-222.0966925010846,
					-6.81091858321895
				]
			]
		},
		{
			"type": "text",
			"version": 8,
			"versionNonce": 1627670327,
			"isDeleted": false,
			"id": "XoO3Mk0l",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2008.994600671029,
			"y": -43.84481724465519,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 12.79998779296875,
			"height": 25,
			"seed": 1152587502,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "6",
			"rawText": "6",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "FrivM8gHegnbQl-uQxgfQ",
			"originalText": "6",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 454,
			"versionNonce": 1437608889,
			"isDeleted": false,
			"id": "5jDABdSQ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1726.7064768448806,
			"y": 18.36359661481015,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 615.6994018554688,
			"height": 150,
			"seed": 371851186,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016423,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1. request to payment service\n2. payment-service toss the request to connected psp service\n3. psp service return the payment result\n4. save the result of 3 data to relation database\n5. find the saved result\n6. return the result of payment status",
			"rawText": "1. request to payment service\n2. payment-service toss the request to connected psp service\n3. psp service return the payment result\n4. save the result of 3 data to relation database\n5. find the saved result\n6. return the result of payment status",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1. request to payment service\n2. payment-service toss the request to connected psp service\n3. psp service return the payment result\n4. save the result of 3 data to relation database\n5. find the saved result\n6. return the result of payment status",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "rectangle",
			"version": 432,
			"versionNonce": 1032079447,
			"isDeleted": false,
			"id": "el6PrYSUQ1bIqazY88vK3",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1716.679697209829,
			"y": 503.13294391279896,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 165,
			"height": 71,
			"seed": 1612488690,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "maejeJHw"
				},
				{
					"id": "JkEkonuQ8NAZuWogXt-iF",
					"type": "arrow"
				},
				{
					"id": "9lLXRgYVIdwoKQwsAaRxb",
					"type": "arrow"
				},
				{
					"id": "7hi4i3cZZegre0tNn3dvF",
					"type": "arrow"
				},
				{
					"id": "SgRPZJfAnz8b5YC4nFT3r",
					"type": "arrow"
				}
			],
			"updated": 1715428016423,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 336,
			"versionNonce": 33836185,
			"isDeleted": false,
			"id": "maejeJHw",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1754.9797384085596,
			"y": 513.632943912799,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 88.39991760253906,
			"height": 50,
			"seed": 1529336242,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Payment-\nService",
			"rawText": "Payment-Service",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "el6PrYSUQ1bIqazY88vK3",
			"originalText": "Payment-Service",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 841,
			"versionNonce": 1218913655,
			"isDeleted": false,
			"id": "JkEkonuQ8NAZuWogXt-iF",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1838.9069762356162,
			"y": 581.6420795334143,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 249.8746541609803,
			"height": 187.60238711846182,
			"seed": 398202610,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "ugfvqKsS"
				}
			],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "el6PrYSUQ1bIqazY88vK3",
				"gap": 7.509135620615325,
				"focus": 0.01718814699992552
			},
			"endBinding": {
				"elementId": "kPy3Tw0EGsVrjnSE9yGhA",
				"gap": 10.429526947504655,
				"focus": -0.7625899596714169
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					109.7229162867132,
					113.06606133766569
				],
				[
					249.8746541609803,
					187.60238711846182
				]
			]
		},
		{
			"type": "text",
			"version": 12,
			"versionNonce": 1424052601,
			"isDeleted": false,
			"id": "ugfvqKsS",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1930.589906865591,
			"y": 682.20814087108,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 36.07997131347656,
			"height": 25,
			"seed": 11671794,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "3-2",
			"rawText": "3-2",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "JkEkonuQ8NAZuWogXt-iF",
			"originalText": "3-2",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 740,
			"versionNonce": 1639014039,
			"isDeleted": false,
			"id": "9lLXRgYVIdwoKQwsAaRxb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1846.2844106480916,
			"y": 581.6436559297088,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 244.42559291485986,
			"height": 125.31359291308854,
			"seed": 2109761714,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "iASbu4P8"
				}
			],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "el6PrYSUQ1bIqazY88vK3",
				"gap": 7.5107120169097925,
				"focus": 0.3154581299728183
			},
			"endBinding": {
				"elementId": "fqlulgRA0kIIgjz54HnEz",
				"gap": 7.325372531149696,
				"focus": -0.7782406402746098
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					134.96071624923752,
					58.708639462665694
				],
				[
					244.42559291485986,
					125.31359291308854
				]
			]
		},
		{
			"type": "text",
			"version": 11,
			"versionNonce": 1401600601,
			"isDeleted": false,
			"id": "iASbu4P8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1967.6151372733057,
			"y": 627.8522953923745,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 27.259979248046875,
			"height": 25,
			"seed": 1742567474,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "3-1",
			"rawText": "3-1",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "9lLXRgYVIdwoKQwsAaRxb",
			"originalText": "3-1",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 499,
			"versionNonce": 190280631,
			"isDeleted": false,
			"id": "W8lHga3TIQdpnzjisa_O6",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2531.2031256886726,
			"y": 488.96905248983126,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 230,
			"height": 62,
			"seed": 1255441010,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "jMzzoFJH"
				},
				{
					"id": "c_L8Tfm8vd_Cmn31nUOT0",
					"type": "arrow"
				},
				{
					"id": "GgtXMXmFYCarYMbcP9gIM",
					"type": "arrow"
				},
				{
					"id": "mFa7Sh7p2JUQrXIzWXxmz",
					"type": "arrow"
				}
			],
			"updated": 1715428016424,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 476,
			"versionNonce": 248776505,
			"isDeleted": false,
			"id": "jMzzoFJH",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2576.40319893086,
			"y": 507.46905248983126,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 139.599853515625,
			"height": 25,
			"seed": 431973426,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Ledger-Service",
			"rawText": "Ledger-Service",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "W8lHga3TIQdpnzjisa_O6",
			"originalText": "Ledger-Service",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 1175,
			"versionNonce": 2109596887,
			"isDeleted": false,
			"id": "c_L8Tfm8vd_Cmn31nUOT0",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2343.4892037914547,
			"y": 713.1740315979175,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 182.23652398579225,
			"height": 158.62647417186383,
			"seed": 342363634,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "e73G2joN"
				}
			],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "fqlulgRA0kIIgjz54HnEz",
				"gap": 12.453827697353518,
				"focus": 0.9649599883713794
			},
			"endBinding": {
				"elementId": "W8lHga3TIQdpnzjisa_O6",
				"gap": 6.542750603427976,
				"focus": 0.4261184398622103
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					82.35702771422086,
					-91.84591237382153
				],
				[
					182.23652398579225,
					-158.62647417186383
				]
			]
		},
		{
			"type": "text",
			"version": 8,
			"versionNonce": 824227865,
			"isDeleted": false,
			"id": "e73G2joN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2419.446237609191,
			"y": 608.828119224096,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 12.79998779296875,
			"height": 25,
			"seed": 1257754798,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "4",
			"rawText": "4",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "c_L8Tfm8vd_Cmn31nUOT0",
			"originalText": "4",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "line",
			"version": 5025,
			"versionNonce": 2021208567,
			"isDeleted": false,
			"id": "XyPtN3hi64NeHosg9ovcd",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2174.5374095491875,
			"y": 402.1345591441837,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 77.09201683999922,
			"height": 99.49948667804088,
			"seed": 265650098,
			"groupIds": [
				"IXggaGLOGhy9zggatIlJq",
				"3uGivbWkJVxQaUOTZquCQ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.2542098813493443,
					75.20117273657175
				],
				[
					0.011896425679918422,
					83.76249969444815
				],
				[
					3.970409367559332,
					87.46174320643391
				],
				[
					17.75573317066317,
					90.59250103325854
				],
				[
					41.05683533152865,
					91.56737225214069
				],
				[
					63.319497586673116,
					90.01084754868091
				],
				[
					75.14781395923075,
					86.28844687220405
				],
				[
					76.81603792670788,
					83.15042405259751
				],
				[
					77.05033394391478,
					76.25776215104557
				],
				[
					76.86643881413028,
					6.3089586511537865
				],
				[
					76.45188016352971,
					-0.2999144698665015
				],
				[
					71.50179495549581,
					-3.9936571317850627
				],
				[
					61.077971898861186,
					-6.132877429442784
				],
				[
					37.32348754161154,
					-7.932114425900202
				],
				[
					18.278415656797975,
					-6.859225353587373
				],
				[
					3.2995959613238286,
					-3.2201165291205287
				],
				[
					-0.04168289608444441,
					-0.045185660461322996
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 2730,
			"versionNonce": 1281641721,
			"isDeleted": false,
			"id": "2i5RNSFH5QPhC5hKERTDd",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2175.061338987462,
			"y": 459.26084280191344,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 77.17198221193564,
			"height": 8.562348957853038,
			"seed": 674150770,
			"groupIds": [
				"IXggaGLOGhy9zggatIlJq",
				"3uGivbWkJVxQaUOTZquCQ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.033150371639873,
					3.413095389435587
				],
				[
					10.801287372573954,
					6.276651055277943
				],
				[
					22.468666942209353,
					8.010803051612635
				],
				[
					40.747074201802775,
					8.168828515515864
				],
				[
					62.077348233027564,
					7.0647721921469495
				],
				[
					74.53446931782398,
					3.04824021069218
				],
				[
					77.17198221193564,
					-0.3935204423371723
				]
			]
		},
		{
			"type": "line",
			"version": 2816,
			"versionNonce": 1418582807,
			"isDeleted": false,
			"id": "JFF1dqfina_4gl6i-0V64",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2174.029481664959,
			"y": 430.29678746669055,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 77.17198221193564,
			"height": 8.562348957853038,
			"seed": 1555741490,
			"groupIds": [
				"IXggaGLOGhy9zggatIlJq",
				"3uGivbWkJVxQaUOTZquCQ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.033150371639873,
					3.413095389435587
				],
				[
					10.801287372573954,
					6.276651055277943
				],
				[
					22.468666942209353,
					8.010803051612635
				],
				[
					40.747074201802775,
					8.168828515515864
				],
				[
					62.077348233027564,
					7.0647721921469495
				],
				[
					74.53446931782398,
					3.04824021069218
				],
				[
					77.17198221193564,
					-0.3935204423371723
				]
			]
		},
		{
			"type": "ellipse",
			"version": 5813,
			"versionNonce": 1747076569,
			"isDeleted": false,
			"id": "pVPpRJWKh3ybPJDyZybbG",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2172.971532682877,
			"y": 395.002290518502,
			"strokeColor": "#000000",
			"backgroundColor": "#fff",
			"width": 76.59753601865496,
			"height": 15.49127539284798,
			"seed": 736134386,
			"groupIds": [
				"IXggaGLOGhy9zggatIlJq",
				"3uGivbWkJVxQaUOTZquCQ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1217,
			"versionNonce": 1450205239,
			"isDeleted": false,
			"id": "U3hpFbyuwohSsk9BVIoa0",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2209.4635197880993,
			"y": 419.4789581984057,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 11.226103154161754,
			"height": 12.183758484455605,
			"seed": 791090866,
			"groupIds": [
				"IXggaGLOGhy9zggatIlJq",
				"3uGivbWkJVxQaUOTZquCQ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1505,
			"versionNonce": 1332617913,
			"isDeleted": false,
			"id": "vz-FFin3styM9f7YN0auE",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2209.814661572033,
			"y": 445.6955724854708,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 11.226103154161754,
			"height": 12.183758484455605,
			"seed": 926249074,
			"groupIds": [
				"IXggaGLOGhy9zggatIlJq",
				"3uGivbWkJVxQaUOTZquCQ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1388,
			"versionNonce": 1074086231,
			"isDeleted": false,
			"id": "4-REzyezfgRsFWLN6OA6U",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.239590202363168,
			"x": 2210.4635197880993,
			"y": 474.46429905677724,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 11.226103154161754,
			"height": 12.183758484455605,
			"seed": 1741853234,
			"groupIds": [
				"IXggaGLOGhy9zggatIlJq",
				"3uGivbWkJVxQaUOTZquCQ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 888,
			"versionNonce": 518742937,
			"isDeleted": false,
			"id": "0Z54R46u",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2190.0894782000455,
			"y": 496.05444065562006,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 45.19486999511719,
			"height": 23.595161071904883,
			"seed": 1407548402,
			"groupIds": [
				"3uGivbWkJVxQaUOTZquCQ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "7hi4i3cZZegre0tNn3dvF",
					"type": "arrow"
				},
				{
					"id": "SgRPZJfAnz8b5YC4nFT3r",
					"type": "arrow"
				},
				{
					"id": "GgtXMXmFYCarYMbcP9gIM",
					"type": "arrow"
				},
				{
					"id": "mFa7Sh7p2JUQrXIzWXxmz",
					"type": "arrow"
				}
			],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"fontSize": 17.4778970902999,
			"fontFamily": 1,
			"text": "Mysql",
			"rawText": "Mysql",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Mysql",
			"lineHeight": 1.350000000000001,
			"baseline": 15
		},
		{
			"type": "arrow",
			"version": 916,
			"versionNonce": 580976247,
			"isDeleted": false,
			"id": "7hi4i3cZZegre0tNn3dvF",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1892.019318214299,
			"y": 521.9772766505444,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 286.98362878661635,
			"height": 25.12056333398334,
			"seed": 427109810,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "xElyqKDr"
				}
			],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "el6PrYSUQ1bIqazY88vK3",
				"gap": 10.339621004469791,
				"focus": -0.004102184122417211
			},
			"endBinding": {
				"elementId": "0Z54R46u",
				"focus": 0.2932168176344287,
				"gap": 11.08653119913015
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					141.77344059912457,
					-25.12056333398334
				],
				[
					286.98362878661635,
					-19.221943666765185
				]
			]
		},
		{
			"type": "text",
			"version": 8,
			"versionNonce": 315459705,
			"isDeleted": false,
			"id": "xElyqKDr",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2032.8011335231345,
			"y": 499.8663048171618,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 5.4199981689453125,
			"height": 25,
			"seed": 367445490,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1",
			"rawText": "1",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "7hi4i3cZZegre0tNn3dvF",
			"originalText": "1",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 818,
			"versionNonce": 1896355735,
			"isDeleted": false,
			"id": "SgRPZJfAnz8b5YC4nFT3r",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2178.8851750417784,
			"y": 524.3335891937561,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 287.23568945258035,
			"height": 24.48558281117255,
			"seed": 2108204914,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "CioNTJZx"
				}
			],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "0Z54R46u",
				"focus": -0.6720921477856456,
				"gap": 11.204303158267066
			},
			"endBinding": {
				"elementId": "el6PrYSUQ1bIqazY88vK3",
				"gap": 9.969788379368993,
				"focus": 0.07009398608738297
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-140.25495876474724,
					24.48558281117255
				],
				[
					-287.23568945258035,
					19.87184619786285
				]
			]
		},
		{
			"type": "text",
			"version": 8,
			"versionNonce": 349704537,
			"isDeleted": false,
			"id": "CioNTJZx",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2028.1473351983009,
			"y": 521.7695122926875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 14.239990234375,
			"height": 25,
			"seed": 1025828274,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "2",
			"rawText": "2",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "SgRPZJfAnz8b5YC4nFT3r",
			"originalText": "2",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 751,
			"versionNonce": 1366232247,
			"isDeleted": false,
			"id": "GgtXMXmFYCarYMbcP9gIM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2243.6847266435584,
			"y": 497.64145852236925,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 282.98091639668155,
			"height": 23.635991879743358,
			"seed": 746570930,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "FR9abEgL"
				}
			],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "0Z54R46u",
				"focus": -0.5788469724561528,
				"gap": 8.400378448395713
			},
			"endBinding": {
				"elementId": "W8lHga3TIQdpnzjisa_O6",
				"gap": 4.537482648432615,
				"focus": -0.2076673416691831
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					141.62169318269844,
					-10.864843590652868
				],
				[
					282.98091639668155,
					12.77114828909049
				]
			]
		},
		{
			"type": "text",
			"version": 8,
			"versionNonce": 173964857,
			"isDeleted": false,
			"id": "FR9abEgL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2378.9951921661177,
			"y": 491.5270326669145,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 12.3599853515625,
			"height": 25,
			"seed": 937871346,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "5",
			"rawText": "5",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "GgtXMXmFYCarYMbcP9gIM",
			"originalText": "5",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 778,
			"versionNonce": 796548567,
			"isDeleted": false,
			"id": "mFa7Sh7p2JUQrXIzWXxmz",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2523.36634672684,
			"y": 528.4349526302376,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 285.0171462703272,
			"height": 24.733674108110677,
			"seed": 558390898,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "AoXB4G1E"
				}
			],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "W8lHga3TIQdpnzjisa_O6",
				"gap": 7.836778961832351,
				"focus": 0.048574548982296586
			},
			"endBinding": {
				"elementId": "0Z54R46u",
				"focus": 0.22039105943372514,
				"gap": 3.064852261350552
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-141.4529517327942,
					12.03001693913859
				],
				[
					-285.0171462703272,
					-12.703657168972086
				]
			]
		},
		{
			"type": "text",
			"version": 8,
			"versionNonce": 1648643865,
			"isDeleted": false,
			"id": "AoXB4G1E",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2374.4577796951926,
			"y": 509.58312404575156,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 12.79998779296875,
			"height": 25,
			"seed": 1781633202,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "6",
			"rawText": "6",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "mFa7Sh7p2JUQrXIzWXxmz",
			"originalText": "6",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 725,
			"versionNonce": 238979831,
			"isDeleted": false,
			"id": "fqlulgRA0kIIgjz54HnEz",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2098.035376094101,
			"y": 684.4561989439067,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 233,
			"height": 48,
			"seed": 760725554,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "LxMVRLdj"
				},
				{
					"id": "9lLXRgYVIdwoKQwsAaRxb",
					"type": "arrow"
				},
				{
					"id": "c_L8Tfm8vd_Cmn31nUOT0",
					"type": "arrow"
				}
			],
			"updated": 1715428016424,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 568,
			"versionNonce": 1660748793,
			"isDeleted": false,
			"id": "LxMVRLdj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2135.9054551346285,
			"y": 695.9561989439067,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 157.2598419189453,
			"height": 25,
			"seed": 1284827634,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "payment.success",
			"rawText": "payment.success",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "fqlulgRA0kIIgjz54HnEz",
			"originalText": "payment.success",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 797,
			"versionNonce": 440407063,
			"isDeleted": false,
			"id": "kPy3Tw0EGsVrjnSE9yGhA",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2099.211157344101,
			"y": 747.1983847981255,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 233,
			"height": 48,
			"seed": 1711725490,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "I0bBm6jB"
				},
				{
					"id": "JkEkonuQ8NAZuWogXt-iF",
					"type": "arrow"
				}
			],
			"updated": 1715428016424,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 656,
			"versionNonce": 948706521,
			"isDeleted": false,
			"id": "I0bBm6jB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2142.7612290604097,
			"y": 758.6983847981255,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 145.8998565673828,
			"height": 25,
			"seed": 1741985138,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "payment.failure",
			"rawText": "payment.failure",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "kPy3Tw0EGsVrjnSE9yGhA",
			"originalText": "payment.failure",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 370,
			"versionNonce": 2071165239,
			"isDeleted": false,
			"id": "35bX-anUOZmgL-0Rj2VBZ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2053.34095811247,
			"y": 633.2911647482051,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 314.3771962107555,
			"height": 246.64586856693924,
			"seed": 1665472306,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 254,
			"versionNonce": 1116019129,
			"isDeleted": false,
			"id": "3SziCpiJ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2070.0158677003524,
			"y": 641.1679508336872,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 58.39996337890625,
			"height": 25,
			"seed": 683630834,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Kafka",
			"rawText": "Kafka",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Kafka",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 489,
			"versionNonce": 1732065879,
			"isDeleted": false,
			"id": "1JdjB5Ni",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1762.703909910171,
			"y": 925.6704916789105,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 671.7193603515625,
			"height": 175,
			"seed": 1978122862,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1. save the result of psp service response\n2. find the saved result\n3-1. if payment success publish the event message to kafka cluster\n3-2. if payment failed publish the event message to kafka cluster\n4. receive the payment success event\n5. find the saved psp result that processing in step.1\n6. save the double-entry ledger data to relation database",
			"rawText": "1. save the result of psp service response\n2. find the saved result\n3-1. if payment success publish the event message to kafka cluster\n3-2. if payment failed publish the event message to kafka cluster\n4. receive the payment success event\n5. find the saved psp result that processing in step.1\n6. save the double-entry ledger data to relation database",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1. save the result of psp service response\n2. find the saved result\n3-1. if payment success publish the event message to kafka cluster\n3-2. if payment failed publish the event message to kafka cluster\n4. receive the payment success event\n5. find the saved psp result that processing in step.1\n6. save the double-entry ledger data to relation database",
			"lineHeight": 1.25,
			"baseline": 168
		},
		{
			"type": "rectangle",
			"version": 403,
			"versionNonce": 571177625,
			"isDeleted": false,
			"id": "NlkdqioGX9od8TG3HCXpC",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3145.6111577761903,
			"y": -233.35950106467783,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 165,
			"height": 71,
			"seed": 694783150,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "Dt8uV3ZB"
				},
				{
					"id": "UHpKmDSUZlnOwD7TK6Ctk",
					"type": "arrow"
				},
				{
					"id": "i4Jm7x8AWjq9VJrLtpp4B",
					"type": "arrow"
				},
				{
					"id": "tNcb6x8NO39Dm54U4gMyi",
					"type": "arrow"
				},
				{
					"id": "kmWKtq_XPW29U6fnHv-AK",
					"type": "arrow"
				},
				{
					"id": "0yjSxTaZahDJwAqoVfZ6X",
					"type": "arrow"
				}
			],
			"updated": 1715428016424,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 304,
			"versionNonce": 1920063351,
			"isDeleted": false,
			"id": "Dt8uV3ZB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3183.911198974921,
			"y": -222.85950106467783,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 88.39991760253906,
			"height": 50,
			"seed": 1110427374,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Payment-\nService",
			"rawText": "Payment-Service",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "NlkdqioGX9od8TG3HCXpC",
			"originalText": "Payment-Service",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 748,
			"versionNonce": 131252089,
			"isDeleted": false,
			"id": "UHpKmDSUZlnOwD7TK6Ctk",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3267.838436801978,
			"y": -154.8503654440625,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 249.8746541609803,
			"height": 187.60238711846205,
			"seed": 595510702,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "oINhVBHG"
				}
			],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "NlkdqioGX9od8TG3HCXpC",
				"gap": 7.509135620615325,
				"focus": 0.017188146999920922
			},
			"endBinding": {
				"elementId": "niKKuu-peoEecxKkcdAik",
				"gap": 10.429526947504655,
				"focus": -0.76258995967142
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					109.72291628671286,
					113.06606133766569
				],
				[
					249.8746541609803,
					187.60238711846205
				]
			]
		},
		{
			"type": "text",
			"version": 40,
			"versionNonce": 592826519,
			"isDeleted": false,
			"id": "oINhVBHG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3359.5213674319525,
			"y": -54.28430410639682,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 36.07997131347656,
			"height": 25,
			"seed": 997316590,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "3-2",
			"rawText": "3-2",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "UHpKmDSUZlnOwD7TK6Ctk",
			"originalText": "3-2",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 644,
			"versionNonce": 1109289049,
			"isDeleted": false,
			"id": "i4Jm7x8AWjq9VJrLtpp4B",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3275.215871214453,
			"y": -154.56946200217783,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 244.42559291486077,
			"height": 125.31359291308868,
			"seed": 389406702,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "RAMgQ8Qb"
				}
			],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "NlkdqioGX9od8TG3HCXpC",
				"gap": 7.7900390625,
				"focus": 0.3193709340992184
			},
			"endBinding": {
				"elementId": "Uc0XZZ70-WYFSf9LP1dPh",
				"gap": 7.325372531149242,
				"focus": -0.7811844717652142
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					134.96071624923752,
					58.708639462665694
				],
				[
					244.42559291486077,
					125.31359291308868
				]
			]
		},
		{
			"type": "text",
			"version": 40,
			"versionNonce": 1134405047,
			"isDeleted": false,
			"id": "RAMgQ8Qb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3396.546597839667,
			"y": -108.36082253951213,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 27.259979248046875,
			"height": 25,
			"seed": 1749694510,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "3-1",
			"rawText": "3-1",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "i4Jm7x8AWjq9VJrLtpp4B",
			"originalText": "3-1",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "line",
			"version": 4993,
			"versionNonce": 180483385,
			"isDeleted": false,
			"id": "9mqu7jYoJW2nGQbdAWL1N",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3603.4688701155487,
			"y": -334.3578858332931,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 77.09201683999922,
			"height": 99.49948667804088,
			"seed": 535263470,
			"groupIds": [
				"pz0hgnPqqMQILbZ9MK-DC",
				"pr-48mTUNbU4d3cXOapJj"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.2542098813493443,
					75.20117273657175
				],
				[
					0.011896425679918422,
					83.76249969444815
				],
				[
					3.970409367559332,
					87.46174320643391
				],
				[
					17.75573317066317,
					90.59250103325854
				],
				[
					41.05683533152865,
					91.56737225214069
				],
				[
					63.319497586673116,
					90.01084754868091
				],
				[
					75.14781395923075,
					86.28844687220405
				],
				[
					76.81603792670788,
					83.15042405259751
				],
				[
					77.05033394391478,
					76.25776215104557
				],
				[
					76.86643881413028,
					6.3089586511537865
				],
				[
					76.45188016352971,
					-0.2999144698665015
				],
				[
					71.50179495549581,
					-3.9936571317850627
				],
				[
					61.077971898861186,
					-6.132877429442784
				],
				[
					37.32348754161154,
					-7.932114425900202
				],
				[
					18.278415656797975,
					-6.859225353587373
				],
				[
					3.2995959613238286,
					-3.2201165291205287
				],
				[
					-0.04168289608444441,
					-0.045185660461322996
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 2698,
			"versionNonce": 1919801047,
			"isDeleted": false,
			"id": "sM4h6Pi7fwyG3-UZRhwwB",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3603.9927995538237,
			"y": -277.2316021755632,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 77.17198221193564,
			"height": 8.562348957853038,
			"seed": 1118186286,
			"groupIds": [
				"pz0hgnPqqMQILbZ9MK-DC",
				"pr-48mTUNbU4d3cXOapJj"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.033150371639873,
					3.413095389435587
				],
				[
					10.801287372573954,
					6.276651055277943
				],
				[
					22.468666942209353,
					8.010803051612635
				],
				[
					40.747074201802775,
					8.168828515515864
				],
				[
					62.077348233027564,
					7.0647721921469495
				],
				[
					74.53446931782398,
					3.04824021069218
				],
				[
					77.17198221193564,
					-0.3935204423371723
				]
			]
		},
		{
			"type": "line",
			"version": 2784,
			"versionNonce": 354477593,
			"isDeleted": false,
			"id": "g-SzMNMa4yvu1jzoFJMcj",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3602.96094223132,
			"y": -306.1956575107862,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 77.17198221193564,
			"height": 8.562348957853038,
			"seed": 2002031982,
			"groupIds": [
				"pz0hgnPqqMQILbZ9MK-DC",
				"pr-48mTUNbU4d3cXOapJj"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.033150371639873,
					3.413095389435587
				],
				[
					10.801287372573954,
					6.276651055277943
				],
				[
					22.468666942209353,
					8.010803051612635
				],
				[
					40.747074201802775,
					8.168828515515864
				],
				[
					62.077348233027564,
					7.0647721921469495
				],
				[
					74.53446931782398,
					3.04824021069218
				],
				[
					77.17198221193564,
					-0.3935204423371723
				]
			]
		},
		{
			"type": "ellipse",
			"version": 5781,
			"versionNonce": 1985668087,
			"isDeleted": false,
			"id": "n8MGFI1tm5NnMWajObCeW",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3601.902993249238,
			"y": -341.4901544589747,
			"strokeColor": "#000000",
			"backgroundColor": "#fff",
			"width": 76.59753601865496,
			"height": 15.49127539284798,
			"seed": 1463531438,
			"groupIds": [
				"pz0hgnPqqMQILbZ9MK-DC",
				"pr-48mTUNbU4d3cXOapJj"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1185,
			"versionNonce": 1546566393,
			"isDeleted": false,
			"id": "XOMS6OKvvyIMmI3lpZddE",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3638.3949803544606,
			"y": -317.01348677907106,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 11.226103154161754,
			"height": 12.183758484455605,
			"seed": 1787073006,
			"groupIds": [
				"pz0hgnPqqMQILbZ9MK-DC",
				"pr-48mTUNbU4d3cXOapJj"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1473,
			"versionNonce": 1332301079,
			"isDeleted": false,
			"id": "osCt2XTTUf7eizaebboGS",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3638.746122138394,
			"y": -290.79687249200595,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 11.226103154161754,
			"height": 12.183758484455605,
			"seed": 1278747694,
			"groupIds": [
				"pz0hgnPqqMQILbZ9MK-DC",
				"pr-48mTUNbU4d3cXOapJj"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1356,
			"versionNonce": 812577753,
			"isDeleted": false,
			"id": "4-pOQUusVDY4cXSIpExbE",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.239590202363168,
			"x": 3639.3949803544606,
			"y": -262.02814592069956,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 11.226103154161754,
			"height": 12.183758484455605,
			"seed": 1312779886,
			"groupIds": [
				"pz0hgnPqqMQILbZ9MK-DC",
				"pr-48mTUNbU4d3cXOapJj"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 858,
			"versionNonce": 151884343,
			"isDeleted": false,
			"id": "BTc4swFA",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3619.0209387664067,
			"y": -240.43800432185674,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 45.19486999511719,
			"height": 23.595161071904883,
			"seed": 493056174,
			"groupIds": [
				"pr-48mTUNbU4d3cXOapJj"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "tNcb6x8NO39Dm54U4gMyi",
					"type": "arrow"
				},
				{
					"id": "kmWKtq_XPW29U6fnHv-AK",
					"type": "arrow"
				},
				{
					"id": "BMqjVJ42WwBvyt1HJi2B-",
					"type": "arrow"
				},
				{
					"id": "ns2hazuz-wehpf-gLxEBd",
					"type": "arrow"
				}
			],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"fontSize": 17.4778970902999,
			"fontFamily": 1,
			"text": "Mysql",
			"rawText": "Mysql",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Mysql",
			"lineHeight": 1.350000000000001,
			"baseline": 15
		},
		{
			"type": "arrow",
			"version": 847,
			"versionNonce": 99946681,
			"isDeleted": false,
			"id": "tNcb6x8NO39Dm54U4gMyi",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3320.95077878066,
			"y": -214.78093523482204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 286.98362878661646,
			"height": 27.62135278407419,
			"seed": 1699556078,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "tj4pX9jP"
				}
			],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "NlkdqioGX9od8TG3HCXpC",
				"gap": 10.339621004469791,
				"focus": 0.041615577000166146
			},
			"endBinding": {
				"elementId": "BTc4swFA",
				"focus": 0.26919960516137276,
				"gap": 11.08653119913015
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					134.2221052103123,
					-27.62135278407419
				],
				[
					286.98362878661646,
					-19.22194363947625
				]
			]
		},
		{
			"type": "text",
			"version": 38,
			"versionNonce": 1277965143,
			"isDeleted": false,
			"id": "tj4pX9jP",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3452.4628849064998,
			"y": -254.90228801889623,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 5.4199981689453125,
			"height": 25,
			"seed": 1171324530,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1",
			"rawText": "1",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "tNcb6x8NO39Dm54U4gMyi",
			"originalText": "1",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 714,
			"versionNonce": 40145305,
			"isDeleted": false,
			"id": "kmWKtq_XPW29U6fnHv-AK",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3608.9379821186576,
			"y": -212.22287509312568,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 288.3570359630976,
			"height": 21.280262005613366,
			"seed": 1954913582,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "j8kWo1HQ"
				}
			],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "BTc4swFA",
				"focus": -0.7622887968443498,
				"gap": 10.082956647749143
			},
			"endBinding": {
				"elementId": "NlkdqioGX9od8TG3HCXpC",
				"gap": 9.969788379369675,
				"focus": 0.1307157218446021
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-143.04433251698038,
					21.280262005613366
				],
				[
					-288.3570359630976,
					19.94942542928979
				]
			]
		},
		{
			"type": "text",
			"version": 38,
			"versionNonce": 823767159,
			"isDeleted": false,
			"id": "j8kWo1HQ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3458.7736544844897,
			"y": -203.4426130875123,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 14.239990234375,
			"height": 25,
			"seed": 2120857394,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016424,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "2",
			"rawText": "2",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "kmWKtq_XPW29U6fnHv-AK",
			"originalText": "2",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 694,
			"versionNonce": 1257305721,
			"isDeleted": false,
			"id": "Uc0XZZ70-WYFSf9LP1dPh",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3526.966836660463,
			"y": -52.03624603357014,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 233,
			"height": 48,
			"seed": 1815584878,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "za9p5H9V"
				},
				{
					"id": "i4Jm7x8AWjq9VJrLtpp4B",
					"type": "arrow"
				},
				{
					"id": "K0YoSRYZjOVbc0nlB2NhN",
					"type": "arrow"
				}
			],
			"updated": 1715428016425,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 536,
			"versionNonce": 1369082263,
			"isDeleted": false,
			"id": "za9p5H9V",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3564.83691570099,
			"y": -40.53624603357014,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 157.2598419189453,
			"height": 25,
			"seed": 1904566958,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016425,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "payment.success",
			"rawText": "payment.success",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "Uc0XZZ70-WYFSf9LP1dPh",
			"originalText": "payment.success",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 766,
			"versionNonce": 308133721,
			"isDeleted": false,
			"id": "niKKuu-peoEecxKkcdAik",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3528.142617910463,
			"y": 10.705939820648723,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 233,
			"height": 48,
			"seed": 73456878,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "KMU7xajg"
				},
				{
					"id": "UHpKmDSUZlnOwD7TK6Ctk",
					"type": "arrow"
				}
			],
			"updated": 1715428016425,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 623,
			"versionNonce": 451100343,
			"isDeleted": false,
			"id": "KMU7xajg",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3571.6926896267714,
			"y": 22.205939820648723,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 145.8998565673828,
			"height": 25,
			"seed": 441650990,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016425,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "payment.failure",
			"rawText": "payment.failure",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "niKKuu-peoEecxKkcdAik",
			"originalText": "payment.failure",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 338,
			"versionNonce": 1727949881,
			"isDeleted": false,
			"id": "CBxt5uyrMBZr9c3sSZEP3",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3482.272418678832,
			"y": -103.20128022927156,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 314.3771962107555,
			"height": 246.64586856693924,
			"seed": 264567150,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1715428016425,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 222,
			"versionNonce": 1603817431,
			"isDeleted": false,
			"id": "wGJfQ9Ab",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3498.9473282667136,
			"y": -95.3244941437896,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 58.39996337890625,
			"height": 25,
			"seed": 1275042734,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016425,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Kafka",
			"rawText": "Kafka",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Kafka",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 655,
			"versionNonce": 1085701401,
			"isDeleted": false,
			"id": "Xs-r8DTLM-vpdQoGI-M9Z",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3961.018377143786,
			"y": -81.0407476387453,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 230,
			"height": 62,
			"seed": 1697379822,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "ZQRn8wyB"
				},
				{
					"id": "K0YoSRYZjOVbc0nlB2NhN",
					"type": "arrow"
				},
				{
					"id": "SJUR2q7GrTu1PepuKAiI0",
					"type": "arrow"
				},
				{
					"id": "BMqjVJ42WwBvyt1HJi2B-",
					"type": "arrow"
				},
				{
					"id": "ns2hazuz-wehpf-gLxEBd",
					"type": "arrow"
				}
			],
			"updated": 1715428016425,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 638,
			"versionNonce": 701381879,
			"isDeleted": false,
			"id": "ZQRn8wyB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3985.0784738845086,
			"y": -62.5407476387453,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 181.8798065185547,
			"height": 25,
			"seed": 1146292270,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016425,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Settlement-Service",
			"rawText": "Settlement-Service",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "Xs-r8DTLM-vpdQoGI-M9Z",
			"originalText": "Settlement-Service",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 739,
			"versionNonce": 1324970489,
			"isDeleted": false,
			"id": "_cTiI1uz9KV9Iv4QMUSTI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3529.5358273332304,
			"y": 70.28486780204946,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 233,
			"height": 48,
			"seed": 1230885486,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "w0osFMEv"
				},
				{
					"id": "SJUR2q7GrTu1PepuKAiI0",
					"type": "arrow"
				},
				{
					"id": "0yjSxTaZahDJwAqoVfZ6X",
					"type": "arrow"
				}
			],
			"updated": 1715428016425,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 601,
			"versionNonce": 1292469783,
			"isDeleted": false,
			"id": "w0osFMEv",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3553.395927125711,
			"y": 81.78486780204946,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 185.27980041503906,
			"height": 25,
			"seed": 1863668910,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016425,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "settlement.success",
			"rawText": "settlement.success",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "_cTiI1uz9KV9Iv4QMUSTI",
			"originalText": "settlement.success",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 1147,
			"versionNonce": 113953497,
			"isDeleted": false,
			"id": "K0YoSRYZjOVbc0nlB2NhN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3772.6974270313353,
			"y": -13.257300540628528,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 182.17554679013438,
			"height": 32.51438619123708,
			"seed": 1864535790,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "ZX99KUzb"
				}
			],
			"updated": 1715428016425,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Uc0XZZ70-WYFSf9LP1dPh",
				"gap": 12.73059037087205,
				"focus": 0.7934212133031746
			},
			"endBinding": {
				"elementId": "Xs-r8DTLM-vpdQoGI-M9Z",
				"gap": 6.14540332231627,
				"focus": 0.44960487660753445
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					104.21621514303433,
					-12.074097019050903
				],
				[
					182.17554679013438,
					-32.51438619123708
				]
			]
		},
		{
			"type": "text",
			"version": 38,
			"versionNonce": 943631159,
			"isDeleted": false,
			"id": "ZX99KUzb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3870.5136482778853,
			"y": -37.83139755967943,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 12.79998779296875,
			"height": 25,
			"seed": 489155122,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016425,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "4",
			"rawText": "4",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "K0YoSRYZjOVbc0nlB2NhN",
			"originalText": "4",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 835,
			"versionNonce": 1891502009,
			"isDeleted": false,
			"id": "SJUR2q7GrTu1PepuKAiI0",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3953.057449662394,
			"y": -21.49987684279911,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 182.98203294497216,
			"height": 123.82274231015882,
			"seed": 1712226606,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "BaTwgiSW"
				}
			],
			"updated": 1715428016425,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Xs-r8DTLM-vpdQoGI-M9Z",
				"gap": 7.960927481391991,
				"focus": 0.6059555037372558
			},
			"endBinding": {
				"elementId": "_cTiI1uz9KV9Iv4QMUSTI",
				"gap": 7.5395893841914585,
				"focus": 0.8599967447294947
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-75.39954877221442,
					66.97795844089988
				],
				[
					-182.98203294497216,
					123.82274231015882
				]
			]
		},
		{
			"type": "text",
			"version": 38,
			"versionNonce": 131214423,
			"isDeleted": false,
			"id": "BaTwgiSW",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3872.2779036367615,
			"y": 32.97808159810077,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 10.759994506835938,
			"height": 25,
			"seed": 382487726,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016425,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "7",
			"rawText": "7",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "SJUR2q7GrTu1PepuKAiI0",
			"originalText": "7",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 644,
			"versionNonce": 922134681,
			"isDeleted": false,
			"id": "0yjSxTaZahDJwAqoVfZ6X",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3522.781557019365,
			"y": 98.75525229206184,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 301.4531868666768,
			"height": 256.22891602649315,
			"seed": 2000825198,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "yAsiC4sd"
				}
			],
			"updated": 1715428016425,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "_cTiI1uz9KV9Iv4QMUSTI",
				"gap": 6.754270313865163,
				"focus": -0.8272176127787955
			},
			"endBinding": {
				"elementId": "NlkdqioGX9od8TG3HCXpC",
				"gap": 4.885837330246545,
				"focus": 0.35413589332271106
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-176.03295114437992,
					-100.72701192370252
				],
				[
					-301.4531868666768,
					-256.22891602649315
				]
			]
		},
		{
			"type": "text",
			"version": 38,
			"versionNonce": 1469614455,
			"isDeleted": false,
			"id": "yAsiC4sd",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3339.098611978501,
			"y": -14.47175963164068,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 15.29998779296875,
			"height": 25,
			"seed": 1709339182,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016425,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "8",
			"rawText": "8",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "0yjSxTaZahDJwAqoVfZ6X",
			"originalText": "8",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 666,
			"versionNonce": 1932012921,
			"isDeleted": false,
			"id": "BMqjVJ42WwBvyt1HJi2B-",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3632.8555504617893,
			"y": -205.3954984077597,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 324.8767215437515,
			"height": 132.0910702667921,
			"seed": 1471284334,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "fs6YoqbQ"
				}
			],
			"updated": 1715428016425,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "BTc4swFA",
				"focus": 1.1858373196019796,
				"gap": 11.447344842192138
			},
			"endBinding": {
				"elementId": "Xs-r8DTLM-vpdQoGI-M9Z",
				"gap": 3.286105138245148,
				"focus": -0.22255934255351725
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					140.44328950929048,
					72.07421357439847
				],
				[
					324.8767215437515,
					132.0910702667921
				]
			]
		},
		{
			"type": "text",
			"version": 38,
			"versionNonce": 1423327895,
			"isDeleted": false,
			"id": "fs6YoqbQ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3767.1188472952986,
			"y": -145.82128483336123,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 12.3599853515625,
			"height": 25,
			"seed": 1155897454,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016425,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "5",
			"rawText": "5",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "BMqjVJ42WwBvyt1HJi2B-",
			"originalText": "5",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 813,
			"versionNonce": 1016469081,
			"isDeleted": false,
			"id": "ns2hazuz-wehpf-gLxEBd",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3966.175708580677,
			"y": -87.22428948773916,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 311.9975285161182,
			"height": 125.26399086818986,
			"seed": 1209222830,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "Bp1LPWp0"
				}
			],
			"updated": 1715428016425,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Xs-r8DTLM-vpdQoGI-M9Z",
				"gap": 6.183541848993855,
				"focus": -0.21251275228063268
			},
			"endBinding": {
				"elementId": "BTc4swFA",
				"focus": 0.6550332971819876,
				"gap": 4.35456289402282
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-142.712306987406,
					-73.14346601653074
				],
				[
					-311.9975285161182,
					-125.26399086818986
				]
			]
		},
		{
			"type": "text",
			"version": 39,
			"versionNonce": 272619447,
			"isDeleted": false,
			"id": "Bp1LPWp0",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3817.0634076967867,
			"y": -172.8677555042699,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 12.79998779296875,
			"height": 25,
			"seed": 298751278,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016425,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "6",
			"rawText": "6",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "ns2hazuz-wehpf-gLxEBd",
			"originalText": "6",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 187,
			"versionNonce": 1981014841,
			"isDeleted": false,
			"id": "zY3wRcFy",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1714.8768887563235,
			"y": 336.25336906699965,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 181.3798370361328,
			"height": 25,
			"seed": 192934702,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016425,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "scenario#2. ledger",
			"rawText": "scenario#2. ledger",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "scenario#2. ledger",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 847,
			"versionNonce": 268028119,
			"isDeleted": false,
			"id": "gZJGyCBk",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3232.2082344555492,
			"y": 193.07715708171486,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 667.9794311523438,
			"height": 125,
			"seed": 680043058,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016425,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1...4 same as #2\n5. find the ledger service...??\n6. \n7. publish settlement complete message to kafka cluster\n8. return the settlement completed message for customer or admin",
			"rawText": "1...4 same as #2\n5. find the ledger service...??\n6. \n7. publish settlement complete message to kafka cluster\n8. return the settlement completed message for customer or admin",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1...4 same as #2\n5. find the ledger service...??\n6. \n7. publish settlement complete message to kafka cluster\n8. return the settlement completed message for customer or admin",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "text",
			"version": 91,
			"versionNonce": 1543836697,
			"isDeleted": false,
			"id": "mEOF6VHO",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 360.1404385944383,
			"y": 654.1439232342863,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 229.2598114013672,
			"height": 125,
			"seed": 814197554,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016425,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "checkout\n\n1. payment_event save\n2. payment_order save\n",
			"rawText": "checkout\n\n1. payment_event save\n2. payment_order save\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "checkout\n\n1. payment_event save\n2. payment_order save\n",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "text",
			"version": 202,
			"versionNonce": 563647991,
			"isDeleted": false,
			"id": "i0R6flDJ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 754.1140244990768,
			"y": 681.2992604699248,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 488.5196533203125,
			"height": 125,
			"seed": 262576754,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715428016425,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "confirm\n1. update payment_event status to EXECUTING\n2. update null fields\n3. check amount is correct\n4. ",
			"rawText": "confirm\n1. update payment_event status to EXECUTING\n2. update null fields\n3. check amount is correct\n4. ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "confirm\n1. update payment_event status to EXECUTING\n2. update null fields\n3. check amount is correct\n4. ",
			"lineHeight": 1.25,
			"baseline": 118
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "hachure",
		"currentItemStrokeWidth": 1,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 405.7121022286992,
		"scrollY": 838.0268058533316,
		"zoom": {
			"value": 0.4
		},
		"currentItemRoundness": "round",
		"gridSize": null,
		"gridColor": {
			"Bold": "#C9C9C9FF",
			"Regular": "#EDEDEDFF"
		},
		"currentStrokeOptions": null,
		"previousGridSize": null,
		"frameRendering": {
			"enabled": true,
			"clip": true,
			"name": true,
			"outline": true
		}
	},
	"files": {}
}
```
%%