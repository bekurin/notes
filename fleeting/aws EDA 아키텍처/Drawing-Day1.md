---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
order service ^nkAhIy3j

invoice service ^VRgsyBQf

fullfillment service ^nf3JB0aQ

forecasting service ^3RRiGojI

invoice service에 변경에 취약하다.

fullfillment service에 장애에 취약하다. ^RS6k9CSm

event store: 장애가 발생하더라도 그 사이에 발생된 이벤트를 저장해둬서 복구되는 즉시 이벤트를 수행한다.
 ^Huzx0TXj

event store ^3FPy039D

event broker ^DFWG3iDi

order service ^vT8eip9l

client ^58G3HcFW

Directed commands: 특정 서비스에게 의존 되는 상세한 명령을 하지 않는다.

Observable events: 컨슈머가 알아들을 수 있는 일반적인 이벤트를 내려준다. ^EaRmg05V

orderCreated ^MomioYKt

orderPicked
orderShipped ^Cec30GiU

returnRequested
retrunReceived ^uAyPvoEk

EVENTS EXAMPLE: 도메인의 목적에 맞춰 이벤트를 나눠야한다. ^ODaH0uw3

Choregraph: 서로가 서로의 이벤트에 관심이 없다. ^uaAkpa4B

orderCreated ^3AYCPTmv

orderPicked
orderShipped ^ppxnJhBX

notification ^4mX70YKZ

EventBridge 

Kafka, rabbitMQ의 Producer는 어느 토픽(타입)으로 보내야할지 알아야한다.
이에 반해 EventBridge는 모든 타입의 이벤트를 동일한 EventBus에 보내면 된다.

Archive:
처리된(?) 기존 이벤트를 저장해둘 수 있는 기능
문제가 생겼을 경우 다시 처리할 수 있다.

Rules:
특정 이벤트에 대한 분기 처리를 할 수 있다.
* 여러 서비스가 하나의 EventBus에 이벤트를 보내고, 
Rules를 활용하여 분기 처리를 하여 올바른 서비스에 요청이 갈 수 있도록 한다.
data의 특정 필드를 사용할 수 있다(?)
 ^DURiqF5v

EventBridge vs SNS
EventBridge: 다양한 서비스와 연동이 가능하다.
SNS: 상대적으로 다양한 서비스와 연동이 가능하지는 않지만 성능이 우수하다. ^5t45LeI8

CloudWatch에 저장되는 로그들을 S3에 일자별로 저장을 하고 싶다.
CloudWatch log stream을 일자별로 export 할 수 있는 옵션이 있나?
 ^wcDdWT3u

Event Store
이벤트를 저장해둬서 service 장애가 발생하더라도 최대한 복구할 수 있도록 한다. ^itIh4jmf

event store ^jXJFho1x

client ^eFkwMK1j

service ^ClFG422H

Event Info

최소한의 정보: 
충분한 정보가 없다면 부가적인 정보를 검색하기 위해서 데이터베이스 조회, API 요청해야한다.
- 강한 의존성이 생긴다. (publisher가 제공하는 API와 spec을 알고 있어야하기 때문에)

모든 정보:
이벤트에 정보를 추가하는 것은 어렵지 않지만 삭제하는 것은 어렵다.
- 어디서 사용하는지 알아야하고, 변경을 위한 시간을 부여해야하기 때문에


처음부터 최소한의 정보를 가지고 이벤트를 구성하고, 모두 subscriber가 필요한 경우에 하나씩 이벤트 정보를 추가하는 것이 좋을 수 있다.
 ^vHMz1a6n

At-least once, Exactly-once

At-lease once: 한번 이상의 이벤트가 발생될 수 있다.
- 중복 이벤트 필터링을 해야한다.
* Event마다 unique key가 발급되어 중복 이벤트를 판별한다.

cache, db에 event key를 저장해두고, 중복 체크를 한다.
ex. redis ttl을 걸어서 특정 기간에 두번 들어온 것에 한해 중복으로 구분한다.

Exactly-once: 한번만 이벤트를 발생시킨다.
- 이벤트 유실에 대비해야한다. ^GpVcf6tC

Ordering sematics
정렬을 지원하기도 하고, 지원하지 않기도 한다.
정렬을 지원하면 성능이 지원하지 않는 서비스에 비해 낮다.
정렬을 지원하더라도 Partition에 따라서만 정렬을 지원하는 것이 대부분이다. ^sexAOEeK

Q&A

Event Bus를 사용할 경우 모든 이벤트를 수용할 수 있다.

이때, Producer는 누가 이벤트를 소비하는지 알 필요가 없다.
하지만 Consumer는 어떤 이벤트를 소비하는지 이해할 필요가 있다. ^l1x8yJea

event bus ^WzTXD9vD

consumer1 ^aE1Bom5t

consumer2 ^GlDPpGYE

consumer3 ^cSnISagX

producer ^sy5dmxwL

all events ^SumqJnQT

Serverless VS EDA ^n7qLTmxH

Event Broker
- SQS, SNS, EventBridge ^kH7dQxQE

Event Publisher
- API Gateway ^zkue0Pir

Event Consumer
- lambda ^MIYGujI0

Aws Lambda
대표적인 서버리스 컴퓨팅 시스템이다. ex. ec2 ^79wYeWri

Event Source
- 데이터 상태 변화
(dynamo db, rds)
- 엔드포인트 요청
(api gateway)
- 리소스 상태 변화
(s3)
- etc ^g0W4mudJ

Aws Lambda
(function) ^OEKRrZrn

request ^ifVouPbx

aws services ^sQsQkIpe

request ^yz7Eq7uL

must config iam roles
short running process에 적합하다.
- memory 사용 시간에 따라 과금이 된다.
- timeout이 존재한다.
security group을 정의할 수 있다. ^85btoOSz

concurrency:
lambda가 동시에 처리할 수 있는 request의 개수

default value: 1,000 for each region, each account ^MKi8TAZR

Labmda Layers
각각의 Labmda 함수가 동일한 코드를 사용하고 있다면 layer를 만들어서 공통화 할 수 있다. ^pduLXUZz

Container Image Support for Lambda
- Dockerfile을 통한 간편한 종속성 관리
- 기존 Container를 다루던 방식과 동일한 작업 방식
- 최대 10GB의 컨테이너 이미지 지원
- AWS에서 만든 이미지를 상속해야한다. ^ipMuKWwT

API Gateway
API를 손쉽게 생성, 게시, 유지 관리, 모니터링 및 보안 유지를 할 수 있도록 하는 완전관리형 서비스 ^6DFc4jnS

HTTP API VS REST API
REST API에서만 caching을 지원한다. ^8wdPSaZh

API Gateway Stages ^0DgRgzGM

alias = prod ^9jCFQEZS

alias = beta ^euiHsmhW

alias = dev ^pIv0QG5R

lambda ^39CWodn5

prod ^vZFFUHRS

beta ^a7PSDRLt

dev ^mSHB6xq4

SQS ^PDXcDw7l

SNS ^M6I8D6vt

- 완전 관리형 게시/구독 서비스
- Push 베이스
- publisher는 Topic에 메시지를 publish
- multiple subscribers
- subscriber는 메시지를 filtering하여 원하는 메시지만 받을 수 있다.

Topic Types
Standard, FIFO

FIFO: 정확히 1회 메시지 전송
- SQS만 같이 사용가능

Standard: 최소 1회 메시지 전송

fire-and-forget 메시지 전송 후 이벤트 삭제
 ^dFctUOwD

- 완전 관리형 메시지 대기열
- pull 베이스
- producer는 queue에 메시지 전송, 
consumer는 polling으로 메시지 취득

Topic Types
Standard, FIFO

SQS는 메시지를 일괄 처리한다.
- processing event's type batch

batch size: 일괄 처리한 메시지의 수
batch window: 일괄 처리를 위해 대기하는 시간 ^oixiyS7B

EventBridge

- event: 시스템에 상태 변화가 있다는 신호
- event bus: config rule and target ^mbRKGbfM

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
			"version": 61,
			"versionNonce": 791634494,
			"isDeleted": false,
			"id": "xSiwhI7MWIBr-GOT61iwh",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -304.75390625,
			"y": -223.224609375,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 78,
			"height": 74,
			"seed": 1344423138,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "nkAhIy3j"
				},
				{
					"id": "UdVJoutYJyh2THybOcjIm",
					"type": "arrow"
				},
				{
					"id": "VCBPrI06FbNMCIOVDXNGB",
					"type": "arrow"
				},
				{
					"id": "69z1HS3PcJXKb7Ln8uc9h",
					"type": "arrow"
				}
			],
			"updated": 1698299542190,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 37,
			"versionNonce": 664627362,
			"isDeleted": false,
			"id": "nkAhIy3j",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -298.8638687133789,
			"y": -211.224609375,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 66.21992492675781,
			"height": 50,
			"seed": 110577534,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542190,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "order \nservice",
			"rawText": "order service",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "xSiwhI7MWIBr-GOT61iwh",
			"originalText": "order service",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "rectangle",
			"version": 131,
			"versionNonce": 969173630,
			"isDeleted": false,
			"id": "Fr8Fcf8yuBGABE6PChdHR",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -77.56640625,
			"y": -343.91796875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 78,
			"height": 74,
			"seed": 645211262,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "VRgsyBQf"
				}
			],
			"updated": 1698299542190,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 32,
			"versionNonce": 49022050,
			"isDeleted": false,
			"id": "VRgsyBQf",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -71.6763687133789,
			"y": -331.91796875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 66.21992492675781,
			"height": 50,
			"seed": 1132547518,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542190,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "invoice\nservice",
			"rawText": "invoice service",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "Fr8Fcf8yuBGABE6PChdHR",
			"originalText": "invoice service",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "rectangle",
			"version": 195,
			"versionNonce": 1963879102,
			"isDeleted": false,
			"id": "0nZR-U2qSMQiVTG74wjuL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -76.09375,
			"y": -237.958984375,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 78,
			"height": 85,
			"seed": 455695266,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "nf3JB0aQ"
				},
				{
					"id": "VCBPrI06FbNMCIOVDXNGB",
					"type": "arrow"
				}
			],
			"updated": 1698299542190,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 38,
			"versionNonce": 2037458978,
			"isDeleted": false,
			"id": "nf3JB0aQ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -70.2037124633789,
			"y": -232.958984375,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 66.21992492675781,
			"height": 75,
			"seed": 337476578,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542190,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "fullfill\nment \nservice",
			"rawText": "fullfillment service",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "0nZR-U2qSMQiVTG74wjuL",
			"originalText": "fullfillment service",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "rectangle",
			"version": 257,
			"versionNonce": 1873699582,
			"isDeleted": false,
			"id": "WdUtgYBSevZBuletY46DH",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -73.15625,
			"y": -124.107421875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 78,
			"height": 85,
			"seed": 1830735678,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "3RRiGojI"
				}
			],
			"updated": 1698299542190,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 57,
			"versionNonce": 1931203554,
			"isDeleted": false,
			"id": "3RRiGojI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -67.2662124633789,
			"y": -119.107421875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 66.21992492675781,
			"height": 75,
			"seed": 1363539170,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542190,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "foreca\nsting \nservice",
			"rawText": "forecasting service",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "WdUtgYBSevZBuletY46DH",
			"originalText": "forecasting service",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 138,
			"versionNonce": 1533693624,
			"isDeleted": false,
			"id": "UdVJoutYJyh2THybOcjIm",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -224.25390625,
			"y": -182.51171875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 153.98046875,
			"height": 102.64453125,
			"seed": 2041550462,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698365022463,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "xSiwhI7MWIBr-GOT61iwh",
				"gap": 2.5,
				"focus": -0.3801936066087405
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					153.98046875,
					102.64453125
				]
			]
		},
		{
			"type": "arrow",
			"version": 140,
			"versionNonce": 1753881528,
			"isDeleted": false,
			"id": "VCBPrI06FbNMCIOVDXNGB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -225.75390625,
			"y": -181.8451223728802,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 145.16796875,
			"height": 9.162690127119788,
			"seed": 1419066210,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698365022465,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "xSiwhI7MWIBr-GOT61iwh",
				"gap": 1,
				"focus": 0.17496000383448077
			},
			"endBinding": {
				"elementId": "0nZR-U2qSMQiVTG74wjuL",
				"gap": 4.4921875,
				"focus": -0.0379443489236609
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
					145.16796875,
					-9.162690127119788
				]
			]
		},
		{
			"type": "arrow",
			"version": 112,
			"versionNonce": 1710172600,
			"isDeleted": false,
			"id": "69z1HS3PcJXKb7Ln8uc9h",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -225.75390625,
			"y": -182.10595425564603,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 152.5,
			"height": 121.17529574435397,
			"seed": 722805602,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698365022464,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "xSiwhI7MWIBr-GOT61iwh",
				"gap": 1,
				"focus": 0.5280602840683124
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					152.5,
					-121.17529574435397
				]
			]
		},
		{
			"type": "text",
			"version": 117,
			"versionNonce": 507364194,
			"isDeleted": false,
			"id": "RS6k9CSm",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 99.25,
			"y": -305.22265625,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 340.5596923828125,
			"height": 75,
			"seed": 230797474,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542190,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "invoice service에 변경에 취약하다.\n\nfullfillment service에 장애에 취약하다.",
			"rawText": "invoice service에 변경에 취약하다.\n\nfullfillment service에 장애에 취약하다.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "invoice service에 변경에 취약하다.\n\nfullfillment service에 장애에 취약하다.",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 314,
			"versionNonce": 1073486782,
			"isDeleted": false,
			"id": "Huzx0TXj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -552.40234375,
			"y": 509.328125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 910.7793579101562,
			"height": 50,
			"seed": 845020862,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542191,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "event store: 장애가 발생하더라도 그 사이에 발생된 이벤트를 저장해둬서 복구되는 즉시 이벤트를 수행한다.\n",
			"rawText": "event store: 장애가 발생하더라도 그 사이에 발생된 이벤트를 저장해둬서 복구되는 즉시 이벤트를 수행한다.\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "event store: 장애가 발생하더라도 그 사이에 발생된 이벤트를 저장해둬서 복구되는 즉시 이벤트를 수행한다.\n",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "rectangle",
			"version": 75,
			"versionNonce": 1647511330,
			"isDeleted": false,
			"id": "PPcxPiC7GqVs9bDHEUUTy",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -233.0340525528967,
			"y": 175.36328125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 127,
			"height": 60,
			"seed": 1050923262,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "DFWG3iDi"
				},
				{
					"id": "Ua9kW3wtLZki-H7g4-2_7",
					"type": "arrow"
				}
			],
			"updated": 1698299542191,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 58,
			"versionNonce": 1404957694,
			"isDeleted": false,
			"id": "DFWG3iDi",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -201.02402752848263,
			"y": 180.36328125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 62.979949951171875,
			"height": 50,
			"seed": 249843298,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542191,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "event \nbroker",
			"rawText": "event broker",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "PPcxPiC7GqVs9bDHEUUTy",
			"originalText": "event broker",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "rectangle",
			"version": 199,
			"versionNonce": 1179243234,
			"isDeleted": false,
			"id": "CKBtkx9KqCwdA7RXO7O28",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 76.61328125,
			"y": 103.57421875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 75,
			"height": 60,
			"seed": 435273278,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "3FPy039D"
				},
				{
					"id": "wrAntbzkZoJpT3hcNwS1c",
					"type": "arrow"
				}
			],
			"updated": 1698299542191,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 36,
			"versionNonce": 2048574526,
			"isDeleted": false,
			"id": "3FPy039D",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 82.62330627441406,
			"y": 108.57421875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 62.979949951171875,
			"height": 50,
			"seed": 410232290,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542191,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "event \nstore",
			"rawText": "event store",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "CKBtkx9KqCwdA7RXO7O28",
			"originalText": "event store",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "rectangle",
			"version": 100,
			"versionNonce": 1561405090,
			"isDeleted": false,
			"id": "hKMVp2BwzUAYGWTiKHlmW",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 140.53515625,
			"y": 68.765625,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 131.16796875,
			"height": 112.4296875,
			"seed": 910695230,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1698299542191,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 277,
			"versionNonce": 351505534,
			"isDeleted": false,
			"id": "A3CWaQL1YCau5n_EdqTar",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 82.8671875,
			"y": 240.0078125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 74.6015625,
			"height": 48.7890625,
			"seed": 161816830,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1698299542191,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 182,
			"versionNonce": 255328866,
			"isDeleted": false,
			"id": "IrkR2cBAoox2VJ597oKAd",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 146.58984375,
			"y": 205.19921875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 131.16796875,
			"height": 112.4296875,
			"seed": 613699902,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1698299542191,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 272,
			"versionNonce": 571034814,
			"isDeleted": false,
			"id": "HIa5oAAztYX4h6bWazk_m",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 79.55859375,
			"y": 384.3984375,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 74.6015625,
			"height": 48.7890625,
			"seed": 662858302,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1698299542191,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 177,
			"versionNonce": 1468884514,
			"isDeleted": false,
			"id": "5Lzuh5xOrF4nVvfLr-PhG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 143.28125,
			"y": 349.58984375,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 131.16796875,
			"height": 112.4296875,
			"seed": 1115058814,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1698299542191,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 92,
			"versionNonce": 848334264,
			"isDeleted": false,
			"id": "wrAntbzkZoJpT3hcNwS1c",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -106.8671875,
			"y": 196.9921875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 182.48046875,
			"height": 59.44557860722006,
			"seed": 1970086462,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698365022466,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "CKBtkx9KqCwdA7RXO7O28",
				"gap": 1,
				"focus": 0.20299164538981473
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
					182.48046875,
					-59.44557860722006
				]
			]
		},
		{
			"type": "arrow",
			"version": 106,
			"versionNonce": 2034099384,
			"isDeleted": false,
			"id": "Ua9kW3wtLZki-H7g4-2_7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -105.0340525528967,
			"y": 205.4201692011029,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 190.8778025528967,
			"height": 60.11889329889709,
			"seed": 930345826,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698365022466,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "PPcxPiC7GqVs9bDHEUUTy",
				"gap": 1,
				"focus": -0.4051610488225299
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					190.8778025528967,
					60.11889329889709
				]
			]
		},
		{
			"type": "arrow",
			"version": 137,
			"versionNonce": 760198462,
			"isDeleted": false,
			"id": "XLEqSn7mVkQW_dTh_SVUn",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -106.48828125,
			"y": 201.27734375,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 186.65234375,
			"height": 213.984375,
			"seed": 222937022,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698299542191,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					186.65234375,
					213.984375
				]
			]
		},
		{
			"type": "rectangle",
			"version": 71,
			"versionNonce": 1486865826,
			"isDeleted": false,
			"id": "uhzBWTZbGfBiY-OOXNrzL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -419.08203125,
			"y": 145.83203125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 120,
			"height": 81,
			"seed": 1221339134,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "vT8eip9l"
				},
				{
					"id": "hRk7DUbJejFYakZyqa0RP",
					"type": "arrow"
				}
			],
			"updated": 1698299542191,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 40,
			"versionNonce": 1449287038,
			"isDeleted": false,
			"id": "vT8eip9l",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -392.1919937133789,
			"y": 161.33203125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 66.21992492675781,
			"height": 50,
			"seed": 1709989246,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542191,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "order \nservice",
			"rawText": "order service",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "uhzBWTZbGfBiY-OOXNrzL",
			"originalText": "order service",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "ellipse",
			"version": 131,
			"versionNonce": 2107294050,
			"isDeleted": false,
			"id": "yCVXnq8ozm1_9Tw7OdGtG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -580.3046875,
			"y": 162.83203125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 90,
			"height": 49,
			"seed": 204133566,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "58G3HcFW"
				},
				{
					"id": "hRk7DUbJejFYakZyqa0RP",
					"type": "arrow"
				}
			],
			"updated": 1698299542191,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 90,
			"versionNonce": 1333132734,
			"isDeleted": false,
			"id": "58G3HcFW",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -560.754467018629,
			"y": 175.0079151109296,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 51.25994873046875,
			"height": 25,
			"seed": 771374306,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542191,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "client",
			"rawText": "client",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "yCVXnq8ozm1_9Tw7OdGtG",
			"originalText": "client",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 111,
			"versionNonce": 1096806840,
			"isDeleted": false,
			"id": "hRk7DUbJejFYakZyqa0RP",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -487.2025439320761,
			"y": 192.52467269677885,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 65.42129393207608,
			"height": 2.3371726967788504,
			"seed": 518567358,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698365022467,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "yCVXnq8ozm1_9Tw7OdGtG",
				"gap": 3.9254038589469857,
				"focus": 0.2814799140673164
			},
			"endBinding": {
				"elementId": "uhzBWTZbGfBiY-OOXNrzL",
				"gap": 2.69921875,
				"focus": -0.037884839853980654
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
					65.42129393207608,
					-2.3371726967788504
				]
			]
		},
		{
			"type": "arrow",
			"version": 65,
			"versionNonce": 1571526142,
			"isDeleted": false,
			"id": "ABNj76J42y8LGyxbLOPJT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -299.6015625,
			"y": 190.1015625,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 66.82421875,
			"height": 2.97265625,
			"seed": 865011938,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698299542191,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					66.82421875,
					2.97265625
				]
			]
		},
		{
			"type": "text",
			"version": 481,
			"versionNonce": 1426018530,
			"isDeleted": false,
			"id": "EaRmg05V",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 596.3813658970746,
			"y": -313.9645191437787,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 657.299560546875,
			"height": 75,
			"seed": 901732542,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542191,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Directed commands: 특정 서비스에게 의존 되는 상세한 명령을 하지 않는다.\n\nObservable events: 컨슈머가 알아들을 수 있는 일반적인 이벤트를 내려준다.",
			"rawText": "Directed commands: 특정 서비스에게 의존 되는 상세한 명령을 하지 않는다.\n\nObservable events: 컨슈머가 알아들을 수 있는 일반적인 이벤트를 내려준다.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Directed commands: 특정 서비스에게 의존 되는 상세한 명령을 하지 않는다.\n\nObservable events: 컨슈머가 알아들을 수 있는 일반적인 이벤트를 내려준다.",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 254,
			"versionNonce": 1258405986,
			"isDeleted": false,
			"id": "MomioYKt",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 614.0848839470007,
			"y": -88.72277548565137,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 129.97987365722656,
			"height": 25,
			"seed": 1639913342,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698310538959,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "orderCreated",
			"rawText": "orderCreated",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "orderCreated",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 334,
			"versionNonce": 795829282,
			"isDeleted": false,
			"id": "Cec30GiU",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 854.7149260777395,
			"y": -86.38358770385213,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 119.05986022949219,
			"height": 50,
			"seed": 105872766,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698310538959,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "orderPicked\norderShipped",
			"rawText": "orderPicked\norderShipped",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "orderPicked\norderShipped",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 352,
			"versionNonce": 1173524450,
			"isDeleted": false,
			"id": "uAyPvoEk",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1080.5158446884707,
			"y": -86.62636996127117,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 162.33984375,
			"height": 50,
			"seed": 545969854,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698310538959,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "returnRequested\nretrunReceived",
			"rawText": "returnRequested\nretrunReceived",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "returnRequested\nretrunReceived",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 318,
			"versionNonce": 824574050,
			"isDeleted": false,
			"id": "ODaH0uw3",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 606.4653852893189,
			"y": -163.24565442375666,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 552.6996459960938,
			"height": 25,
			"seed": 1995533118,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542191,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "EVENTS EXAMPLE: 도메인의 목적에 맞춰 이벤트를 나눠야한다.",
			"rawText": "EVENTS EXAMPLE: 도메인의 목적에 맞춰 이벤트를 나눠야한다.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "EVENTS EXAMPLE: 도메인의 목적에 맞춰 이벤트를 나눠야한다.",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 251,
			"versionNonce": 1117406114,
			"isDeleted": false,
			"id": "QZAnGUdDa8_7SOXy62alT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 595.9879715527186,
			"y": -99.08148513553004,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 174.84946958121168,
			"height": 103.64490179817261,
			"seed": 1026967138,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1698310538959,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 282,
			"versionNonce": 2140503906,
			"isDeleted": false,
			"id": "SsdwC6sWcAAjbxVBMfIQP",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 831.7757877461074,
			"y": -101.65574780149694,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 157.38070810691852,
			"height": 134.23546623297068,
			"seed": 2002411554,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1698310538959,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 260,
			"versionNonce": 959660834,
			"isDeleted": false,
			"id": "xDRRH6wh8J_zNywAGQkFE",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1069.024151170636,
			"y": -100.75398513108337,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 212.39979206202202,
			"height": 163.74699841257302,
			"seed": 1403555362,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1698310538959,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 357,
			"versionNonce": 537317346,
			"isDeleted": false,
			"id": "uaAkpa4B",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 619.1363230760862,
			"y": 141.63773169748765,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 424.89971923828125,
			"height": 25,
			"seed": 1264261950,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542192,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Choregraph: 서로가 서로의 이벤트에 관심이 없다.",
			"rawText": "Choregraph: 서로가 서로의 이벤트에 관심이 없다.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Choregraph: 서로가 서로의 이벤트에 관심이 없다.",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 379,
			"versionNonce": 1685591870,
			"isDeleted": false,
			"id": "3AYCPTmv",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 622.7201614324072,
			"y": 205.35926760714415,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 129.97987365722656,
			"height": 25,
			"seed": 491957310,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542192,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "orderCreated",
			"rawText": "orderCreated",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "orderCreated",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 396,
			"versionNonce": 1344701346,
			"isDeleted": false,
			"id": "ppxnJhBX",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 920.5388672524741,
			"y": 202.12543159564677,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 119.05986022949219,
			"height": 50,
			"seed": 1492022398,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542192,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "orderPicked\norderShipped",
			"rawText": "orderPicked\norderShipped",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "orderPicked\norderShipped",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "rectangle",
			"version": 377,
			"versionNonce": 237928318,
			"isDeleted": false,
			"id": "ogRm4icSmr0LMcCoscUUm",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 604.6232490381249,
			"y": 195.00055795726553,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 174.84946958121168,
			"height": 103.64490179817261,
			"seed": 1986475198,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "-RRucL0qpS9qI7Ro_wroI",
					"type": "arrow"
				}
			],
			"updated": 1698299542192,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 302,
			"versionNonce": 295288674,
			"isDeleted": false,
			"id": "miHLWLXXP79wukRaiSZQW",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 897.8868972666162,
			"y": 187.0455791903097,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 157.38070810691852,
			"height": 134.23546623297068,
			"seed": 526249214,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "-RRucL0qpS9qI7Ro_wroI",
					"type": "arrow"
				}
			],
			"updated": 1698299542192,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 530,
			"versionNonce": 1030610878,
			"isDeleted": false,
			"id": "-RRucL0qpS9qI7Ro_wroI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 779.8311375112952,
			"y": 219.94265073410838,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 114.76208110419373,
			"height": 0.4507066739123502,
			"seed": 617764514,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698299542192,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "4mX70YKZ",
				"focus": 1.787980448911393,
				"gap": 10.473476866573947
			},
			"endBinding": {
				"elementId": "miHLWLXXP79wukRaiSZQW",
				"focus": 0.5161308345826235,
				"gap": 3.2936786511272658
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
					114.76208110419373,
					-0.4507066739123502
				]
			]
		},
		{
			"type": "text",
			"version": 267,
			"versionNonce": 11502370,
			"isDeleted": false,
			"id": "4mX70YKZ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 785.7547109398569,
			"y": 184.46917386753444,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 109.67988586425781,
			"height": 25,
			"seed": 677507042,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "-RRucL0qpS9qI7Ro_wroI",
					"type": "arrow"
				}
			],
			"updated": 1698299542192,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "notification",
			"rawText": "notification",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "notification",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 818,
			"versionNonce": 1180121086,
			"isDeleted": false,
			"id": "DURiqF5v",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 609.6741602192413,
			"y": 399.47315094024054,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 701.0394897460938,
			"height": 375,
			"seed": 1498983166,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542192,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "EventBridge \n\nKafka, rabbitMQ의 Producer는 어느 토픽(타입)으로 보내야할지 알아야한다.\n이에 반해 EventBridge는 모든 타입의 이벤트를 동일한 EventBus에 보내면 된다.\n\nArchive:\n처리된(?) 기존 이벤트를 저장해둘 수 있는 기능\n문제가 생겼을 경우 다시 처리할 수 있다.\n\nRules:\n특정 이벤트에 대한 분기 처리를 할 수 있다.\n* 여러 서비스가 하나의 EventBus에 이벤트를 보내고, \nRules를 활용하여 분기 처리를 하여 올바른 서비스에 요청이 갈 수 있도록 한다.\ndata의 특정 필드를 사용할 수 있다(?)\n",
			"rawText": "EventBridge \n\nKafka, rabbitMQ의 Producer는 어느 토픽(타입)으로 보내야할지 알아야한다.\n이에 반해 EventBridge는 모든 타입의 이벤트를 동일한 EventBus에 보내면 된다.\n\nArchive:\n처리된(?) 기존 이벤트를 저장해둘 수 있는 기능\n문제가 생겼을 경우 다시 처리할 수 있다.\n\nRules:\n특정 이벤트에 대한 분기 처리를 할 수 있다.\n* 여러 서비스가 하나의 EventBus에 이벤트를 보내고, \nRules를 활용하여 분기 처리를 하여 올바른 서비스에 요청이 갈 수 있도록 한다.\ndata의 특정 필드를 사용할 수 있다(?)\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "EventBridge \n\nKafka, rabbitMQ의 Producer는 어느 토픽(타입)으로 보내야할지 알아야한다.\n이에 반해 EventBridge는 모든 타입의 이벤트를 동일한 EventBus에 보내면 된다.\n\nArchive:\n처리된(?) 기존 이벤트를 저장해둘 수 있는 기능\n문제가 생겼을 경우 다시 처리할 수 있다.\n\nRules:\n특정 이벤트에 대한 분기 처리를 할 수 있다.\n* 여러 서비스가 하나의 EventBus에 이벤트를 보내고, \nRules를 활용하여 분기 처리를 하여 올바른 서비스에 요청이 갈 수 있도록 한다.\ndata의 특정 필드를 사용할 수 있다(?)\n",
			"lineHeight": 1.25,
			"baseline": 368
		},
		{
			"type": "text",
			"version": 292,
			"versionNonce": 1473695458,
			"isDeleted": false,
			"id": "5t45LeI8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 608.047782739442,
			"y": 776.7590933900054,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 646.5195922851562,
			"height": 75,
			"seed": 2078232574,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542192,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "EventBridge vs SNS\nEventBridge: 다양한 서비스와 연동이 가능하다.\nSNS: 상대적으로 다양한 서비스와 연동이 가능하지는 않지만 성능이 우수하다.",
			"rawText": "EventBridge vs SNS\nEventBridge: 다양한 서비스와 연동이 가능하다.\nSNS: 상대적으로 다양한 서비스와 연동이 가능하지는 않지만 성능이 우수하다.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "EventBridge vs SNS\nEventBridge: 다양한 서비스와 연동이 가능하다.\nSNS: 상대적으로 다양한 서비스와 연동이 가능하지는 않지만 성능이 우수하다.",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 499,
			"versionNonce": 567037154,
			"isDeleted": false,
			"id": "wcDdWT3u",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -501.71519729865605,
			"y": -456.23156173798554,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 610.0396118164062,
			"height": 75,
			"seed": 462398334,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698310528592,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "CloudWatch에 저장되는 로그들을 S3에 일자별로 저장을 하고 싶다.\nCloudWatch log stream을 일자별로 export 할 수 있는 옵션이 있나?\n",
			"rawText": "CloudWatch에 저장되는 로그들을 S3에 일자별로 저장을 하고 싶다.\nCloudWatch log stream을 일자별로 export 할 수 있는 옵션이 있나?\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "CloudWatch에 저장되는 로그들을 S3에 일자별로 저장을 하고 싶다.\nCloudWatch log stream을 일자별로 export 할 수 있는 옵션이 있나?\n",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 151,
			"versionNonce": 731816610,
			"isDeleted": false,
			"id": "itIh4jmf",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1494.0570474377437,
			"y": -317.5433311608151,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 680.6995239257812,
			"height": 50,
			"seed": 1063461154,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542192,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Event Store\n이벤트를 저장해둬서 service 장애가 발생하더라도 최대한 복구할 수 있도록 한다.",
			"rawText": "Event Store\n이벤트를 저장해둬서 service 장애가 발생하더라도 최대한 복구할 수 있도록 한다.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Event Store\n이벤트를 저장해둬서 service 장애가 발생하더라도 최대한 복구할 수 있도록 한다.",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "rectangle",
			"version": 154,
			"versionNonce": 1561055358,
			"isDeleted": false,
			"id": "dnLlGvnRQDobpKVItB8df",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1646.492730200923,
			"y": -239.27947934963916,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 196.4391373654871,
			"height": 39.32008296982349,
			"seed": 33741602,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "-5rYgqVqDH8NdYmW-H2UG",
					"type": "arrow"
				},
				{
					"id": "VDp71qdNRYmwcgn9aK3wf",
					"type": "arrow"
				}
			],
			"updated": 1698299542192,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 193,
			"versionNonce": 649461346,
			"isDeleted": false,
			"id": "eCQRvib6zwqHlal2WdNpJ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1663.069525675253,
			"y": -231.76268369102004,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 21.661779664089636,
			"height": 23.837444541300385,
			"seed": 1718196386,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698299542192,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 206,
			"versionNonce": 1182339262,
			"isDeleted": false,
			"id": "d4NaDB8Mr0q9WHvmjZkm0",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1700.6060694143396,
			"y": -230.1878564979227,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 21.661779664089636,
			"height": 23.837444541300385,
			"seed": 1614621886,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698299542192,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 252,
			"versionNonce": 1173086754,
			"isDeleted": false,
			"id": "VFOA55nNU7FPM3E_L2DHV",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1736.0270320446268,
			"y": -229.40676750857523,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 21.661779664089636,
			"height": 23.837444541300385,
			"seed": 1289798306,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698299542192,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 235,
			"versionNonce": 1221871870,
			"isDeleted": false,
			"id": "szhsIX9qHVfeAf2rntml-",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1769.4557434065382,
			"y": -232.2117308023048,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 21.661779664089636,
			"height": 23.837444541300385,
			"seed": 1890021246,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698299542192,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 112,
			"versionNonce": 338644450,
			"isDeleted": false,
			"id": "jXJFho1x",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1678.5932740505837,
			"y": -187.62325003388668,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 115.7598876953125,
			"height": 25,
			"seed": 209146686,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542192,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "event store",
			"rawText": "event store",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "event store",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 77,
			"versionNonce": 60717374,
			"isDeleted": false,
			"id": "eFkwMK1j",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1504.6223037673385,
			"y": -224.28383567560806,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 51.25994873046875,
			"height": 25,
			"seed": 136748066,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "-5rYgqVqDH8NdYmW-H2UG",
					"type": "arrow"
				}
			],
			"updated": 1698299542192,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "client",
			"rawText": "client",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "client",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 121,
			"versionNonce": 1720664482,
			"isDeleted": false,
			"id": "ClFG422H",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1956.2245563613994,
			"y": -232.6196679667818,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 66.21992492675781,
			"height": 25,
			"seed": 550779298,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "VDp71qdNRYmwcgn9aK3wf",
					"type": "arrow"
				}
			],
			"updated": 1698299542192,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "service",
			"rawText": "service",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "service",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 254,
			"versionNonce": 2117640574,
			"isDeleted": false,
			"id": "-5rYgqVqDH8NdYmW-H2UG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1565.5915171868494,
			"y": -219.4202127378898,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 76.32535970400977,
			"height": 2.6025758632913494,
			"seed": 795002558,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698299542192,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "eFkwMK1j",
				"focus": -0.48088768202558374,
				"gap": 9.70926468904213
			},
			"endBinding": {
				"elementId": "dnLlGvnRQDobpKVItB8df",
				"focus": 0.25678948901090753,
				"gap": 4.575853310063849
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
					76.32535970400977,
					-2.6025758632913494
				]
			]
		},
		{
			"type": "arrow",
			"version": 284,
			"versionNonce": 406502754,
			"isDeleted": false,
			"id": "VDp71qdNRYmwcgn9aK3wf",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1843.8615848249856,
			"y": -221.4662231674761,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 111.27197679420783,
			"height": 0.5945130769122215,
			"seed": 306568994,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698299542192,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "dnLlGvnRQDobpKVItB8df",
				"focus": -0.06524915886477896,
				"gap": 1
			},
			"endBinding": {
				"elementId": "ClFG422H",
				"focus": 0.16753303456718,
				"gap": 1.0909947422060213
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
					111.27197679420783,
					-0.5945130769122215
				]
			]
		},
		{
			"type": "text",
			"version": 787,
			"versionNonce": 736346558,
			"isDeleted": false,
			"id": "vHMz1a6n",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1509.3372984358282,
			"y": -87.53001646778938,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1158.8792724609375,
			"height": 325,
			"seed": 267826786,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542193,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Event Info\n\n최소한의 정보: \n충분한 정보가 없다면 부가적인 정보를 검색하기 위해서 데이터베이스 조회, API 요청해야한다.\n- 강한 의존성이 생긴다. (publisher가 제공하는 API와 spec을 알고 있어야하기 때문에)\n\n모든 정보:\n이벤트에 정보를 추가하는 것은 어렵지 않지만 삭제하는 것은 어렵다.\n- 어디서 사용하는지 알아야하고, 변경을 위한 시간을 부여해야하기 때문에\n\n\n처음부터 최소한의 정보를 가지고 이벤트를 구성하고, 모두 subscriber가 필요한 경우에 하나씩 이벤트 정보를 추가하는 것이 좋을 수 있다.\n",
			"rawText": "Event Info\n\n최소한의 정보: \n충분한 정보가 없다면 부가적인 정보를 검색하기 위해서 데이터베이스 조회, API 요청해야한다.\n- 강한 의존성이 생긴다. (publisher가 제공하는 API와 spec을 알고 있어야하기 때문에)\n\n모든 정보:\n이벤트에 정보를 추가하는 것은 어렵지 않지만 삭제하는 것은 어렵다.\n- 어디서 사용하는지 알아야하고, 변경을 위한 시간을 부여해야하기 때문에\n\n\n처음부터 최소한의 정보를 가지고 이벤트를 구성하고, 모두 subscriber가 필요한 경우에 하나씩 이벤트 정보를 추가하는 것이 좋을 수 있다.\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Event Info\n\n최소한의 정보: \n충분한 정보가 없다면 부가적인 정보를 검색하기 위해서 데이터베이스 조회, API 요청해야한다.\n- 강한 의존성이 생긴다. (publisher가 제공하는 API와 spec을 알고 있어야하기 때문에)\n\n모든 정보:\n이벤트에 정보를 추가하는 것은 어렵지 않지만 삭제하는 것은 어렵다.\n- 어디서 사용하는지 알아야하고, 변경을 위한 시간을 부여해야하기 때문에\n\n\n처음부터 최소한의 정보를 가지고 이벤트를 구성하고, 모두 subscriber가 필요한 경우에 하나씩 이벤트 정보를 추가하는 것이 좋을 수 있다.\n",
			"lineHeight": 1.25,
			"baseline": 318
		},
		{
			"type": "text",
			"version": 586,
			"versionNonce": 1182843170,
			"isDeleted": false,
			"id": "GpVcf6tC",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1512.085340264747,
			"y": 288.6987298060411,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 666.9595336914062,
			"height": 275,
			"seed": 1385580158,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542193,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "At-least once, Exactly-once\n\nAt-lease once: 한번 이상의 이벤트가 발생될 수 있다.\n- 중복 이벤트 필터링을 해야한다.\n* Event마다 unique key가 발급되어 중복 이벤트를 판별한다.\n\ncache, db에 event key를 저장해두고, 중복 체크를 한다.\nex. redis ttl을 걸어서 특정 기간에 두번 들어온 것에 한해 중복으로 구분한다.\n\nExactly-once: 한번만 이벤트를 발생시킨다.\n- 이벤트 유실에 대비해야한다.",
			"rawText": "At-least once, Exactly-once\n\nAt-lease once: 한번 이상의 이벤트가 발생될 수 있다.\n- 중복 이벤트 필터링을 해야한다.\n* Event마다 unique key가 발급되어 중복 이벤트를 판별한다.\n\ncache, db에 event key를 저장해두고, 중복 체크를 한다.\nex. redis ttl을 걸어서 특정 기간에 두번 들어온 것에 한해 중복으로 구분한다.\n\nExactly-once: 한번만 이벤트를 발생시킨다.\n- 이벤트 유실에 대비해야한다.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "At-least once, Exactly-once\n\nAt-lease once: 한번 이상의 이벤트가 발생될 수 있다.\n- 중복 이벤트 필터링을 해야한다.\n* Event마다 unique key가 발급되어 중복 이벤트를 판별한다.\n\ncache, db에 event key를 저장해두고, 중복 체크를 한다.\nex. redis ttl을 걸어서 특정 기간에 두번 들어온 것에 한해 중복으로 구분한다.\n\nExactly-once: 한번만 이벤트를 발생시킨다.\n- 이벤트 유실에 대비해야한다.",
			"lineHeight": 1.25,
			"baseline": 268
		},
		{
			"type": "text",
			"version": 345,
			"versionNonce": 1874909694,
			"isDeleted": false,
			"id": "sexAOEeK",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1510.2480418727982,
			"y": 614.2483985767037,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 646.8195190429688,
			"height": 100,
			"seed": 2071691390,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542193,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Ordering sematics\n정렬을 지원하기도 하고, 지원하지 않기도 한다.\n정렬을 지원하면 성능이 지원하지 않는 서비스에 비해 낮다.\n정렬을 지원하더라도 Partition에 따라서만 정렬을 지원하는 것이 대부분이다.",
			"rawText": "Ordering sematics\n정렬을 지원하기도 하고, 지원하지 않기도 한다.\n정렬을 지원하면 성능이 지원하지 않는 서비스에 비해 낮다.\n정렬을 지원하더라도 Partition에 따라서만 정렬을 지원하는 것이 대부분이다.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Ordering sematics\n정렬을 지원하기도 하고, 지원하지 않기도 한다.\n정렬을 지원하면 성능이 지원하지 않는 서비스에 비해 낮다.\n정렬을 지원하더라도 Partition에 따라서만 정렬을 지원하는 것이 대부분이다.",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "text",
			"version": 302,
			"versionNonce": 214977762,
			"isDeleted": false,
			"id": "l1x8yJea",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1515.7932066442122,
			"y": 766.0894680636097,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 561.099609375,
			"height": 150,
			"seed": 357202558,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542193,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Q&A\n\nEvent Bus를 사용할 경우 모든 이벤트를 수용할 수 있다.\n\n이때, Producer는 누가 이벤트를 소비하는지 알 필요가 없다.\n하지만 Consumer는 어떤 이벤트를 소비하는지 이해할 필요가 있다.",
			"rawText": "Q&A\n\nEvent Bus를 사용할 경우 모든 이벤트를 수용할 수 있다.\n\n이때, Producer는 누가 이벤트를 소비하는지 알 필요가 없다.\n하지만 Consumer는 어떤 이벤트를 소비하는지 이해할 필요가 있다.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Q&A\n\nEvent Bus를 사용할 경우 모든 이벤트를 수용할 수 있다.\n\n이때, Producer는 누가 이벤트를 소비하는지 알 필요가 없다.\n하지만 Consumer는 어떤 이벤트를 소비하는지 이해할 필요가 있다.",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "rectangle",
			"version": 313,
			"versionNonce": 550562366,
			"isDeleted": false,
			"id": "I7PgdknCFDmSTge0QLfQB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1715.8926493482181,
			"y": 1011.065144707218,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 99,
			"height": 60,
			"seed": 914138722,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "WzTXD9vD"
				},
				{
					"id": "E3SfM5-V8Seclxip7INrJ",
					"type": "arrow"
				},
				{
					"id": "UC2FDoMaAoPmNVkGDYPgz",
					"type": "arrow"
				},
				{
					"id": "HTk5nopAefyBwfzJBgij0",
					"type": "arrow"
				},
				{
					"id": "WjrK2Yhk2wfpfk1_MzFt7",
					"type": "arrow"
				}
			],
			"updated": 1698299542193,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 284,
			"versionNonce": 1085825186,
			"isDeleted": false,
			"id": "WzTXD9vD",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1733.9026743726322,
			"y": 1016.065144707218,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 62.979949951171875,
			"height": 50,
			"seed": 797792610,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542193,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "event \nbus",
			"rawText": "event bus",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "I7PgdknCFDmSTge0QLfQB",
			"originalText": "event bus",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "rectangle",
			"version": 156,
			"versionNonce": 234156670,
			"isDeleted": false,
			"id": "-7MFZ8nqCEjjzoMWXNO0Q",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1885.0883572706866,
			"y": 949.8028420490652,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 101,
			"height": 40,
			"seed": 809939582,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "aE1Bom5t"
				},
				{
					"id": "UC2FDoMaAoPmNVkGDYPgz",
					"type": "arrow"
				}
			],
			"updated": 1698299542193,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 113,
			"versionNonce": 770178146,
			"isDeleted": false,
			"id": "aE1Bom5t",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1890.438401521175,
			"y": 957.3028420490652,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 90.29991149902344,
			"height": 25,
			"seed": 138449058,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542193,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "consumer1",
			"rawText": "consumer1",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "-7MFZ8nqCEjjzoMWXNO0Q",
			"originalText": "consumer1",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 289,
			"versionNonce": 32371390,
			"isDeleted": false,
			"id": "H0BX0ZEa5-jRmdSVp32Ad",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1880.3830711369435,
			"y": 1023.3623582495229,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 115,
			"height": 35,
			"seed": 535232254,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "GlDPpGYE"
				},
				{
					"id": "HTk5nopAefyBwfzJBgij0",
					"type": "arrow"
				}
			],
			"updated": 1698299542193,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 259,
			"versionNonce": 1378754594,
			"isDeleted": false,
			"id": "GlDPpGYE",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1888.323119354717,
			"y": 1028.362358249523,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 99.11990356445312,
			"height": 25,
			"seed": 317353790,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542193,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "consumer2",
			"rawText": "consumer2",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "H0BX0ZEa5-jRmdSVp32Ad",
			"originalText": "consumer2",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 234,
			"versionNonce": 1197271806,
			"isDeleted": false,
			"id": "Or7pYipdESw6afeB9Oxwv",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1887.22941070905,
			"y": 1089.58676732837,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 115,
			"height": 35,
			"seed": 1601798946,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "cSnISagX"
				},
				{
					"id": "WjrK2Yhk2wfpfk1_MzFt7",
					"type": "arrow"
				}
			],
			"updated": 1698299542193,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 209,
			"versionNonce": 427412450,
			"isDeleted": false,
			"id": "cSnISagX",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1895.4794564854171,
			"y": 1094.58676732837,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 98.49990844726562,
			"height": 25,
			"seed": 1298190050,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542193,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "consumer3",
			"rawText": "consumer3",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "Or7pYipdESw6afeB9Oxwv",
			"originalText": "consumer3",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 199,
			"versionNonce": 750967614,
			"isDeleted": false,
			"id": "djbS8kN8EVbqlLKa5Hq3x",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1521.2399858925567,
			"y": 1031.5959982710058,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 110,
			"height": 35,
			"seed": 1521255998,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "sy5dmxwL"
				},
				{
					"id": "E3SfM5-V8Seclxip7INrJ",
					"type": "arrow"
				}
			],
			"updated": 1698299542193,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 152,
			"versionNonce": 433717154,
			"isDeleted": false,
			"id": "sy5dmxwL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1535.310031363748,
			"y": 1036.5959982710058,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 81.85990905761719,
			"height": 25,
			"seed": 1899377726,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542193,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "producer",
			"rawText": "producer",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "djbS8kN8EVbqlLKa5Hq3x",
			"originalText": "producer",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 428,
			"versionNonce": 107577784,
			"isDeleted": false,
			"id": "E3SfM5-V8Seclxip7INrJ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1635.606933402088,
			"y": 1047.8444835226696,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 78.66795959297997,
			"height": 4.315650615945287,
			"seed": 1156790562,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698365022470,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "djbS8kN8EVbqlLKa5Hq3x",
				"gap": 4.366947509531428,
				"focus": 0.09773729712985961
			},
			"endBinding": {
				"elementId": "I7PgdknCFDmSTge0QLfQB",
				"gap": 1.617756353150071,
				"focus": 0.010410472477346094
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
					78.66795959297997,
					-4.315650615945287
				]
			]
		},
		{
			"type": "arrow",
			"version": 367,
			"versionNonce": 2130684856,
			"isDeleted": false,
			"id": "UC2FDoMaAoPmNVkGDYPgz",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1820.0999527747585,
			"y": 1034.3578943136122,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 59.874024814326276,
			"height": 64.28191745746994,
			"seed": 1176060450,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698365022469,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "I7PgdknCFDmSTge0QLfQB",
				"gap": 5.20730342654042,
				"focus": 0.6257513796881441
			},
			"endBinding": {
				"elementId": "-7MFZ8nqCEjjzoMWXNO0Q",
				"gap": 5.114379681601804,
				"focus": 0.800826205031199
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
					59.874024814326276,
					-64.28191745746994
				]
			]
		},
		{
			"type": "arrow",
			"version": 322,
			"versionNonce": 887233976,
			"isDeleted": false,
			"id": "HTk5nopAefyBwfzJBgij0",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1822.335345537935,
			"y": 1048.7423951731162,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 55.473319929263425,
			"height": 6.035919848479125,
			"seed": 270362302,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698365022469,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "I7PgdknCFDmSTge0QLfQB",
				"gap": 7.442696189716571,
				"focus": 0.39204935885144276
			},
			"endBinding": {
				"elementId": "H0BX0ZEa5-jRmdSVp32Ad",
				"gap": 2.5744056697453743,
				"focus": 0.19752270692587975
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
					55.473319929263425,
					-6.035919848479125
				]
			]
		},
		{
			"type": "arrow",
			"version": 377,
			"versionNonce": 642781112,
			"isDeleted": false,
			"id": "WjrK2Yhk2wfpfk1_MzFt7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1822.8313008455202,
			"y": 1057.6462304958945,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 57.89559440254425,
			"height": 49.48412050831075,
			"seed": 998277538,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698365022470,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "I7PgdknCFDmSTge0QLfQB",
				"gap": 7.938651497302089,
				"focus": -0.44963691989114846
			},
			"endBinding": {
				"elementId": "Or7pYipdESw6afeB9Oxwv",
				"gap": 6.502515460985478,
				"focus": -0.8214651845735879
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
					57.89559440254425,
					49.48412050831075
				]
			]
		},
		{
			"type": "text",
			"version": 167,
			"versionNonce": 1833392766,
			"isDeleted": false,
			"id": "SumqJnQT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1611.859819532472,
			"y": 1000.2070587314909,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 97.69992065429688,
			"height": 25,
			"seed": 190280930,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698300928164,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "all events",
			"rawText": "all events",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "all events",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 34,
			"versionNonce": 837536482,
			"isDeleted": false,
			"id": "n7qLTmxH",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -355.41905830161704,
			"y": 1192.2422477981513,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 331.77587890625,
			"height": 45,
			"seed": 1532590014,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542193,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Serverless VS EDA",
			"rawText": "Serverless VS EDA",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Serverless VS EDA",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 124,
			"versionNonce": 196365374,
			"isDeleted": false,
			"id": "kH7dQxQE",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -90.4977449566511,
			"y": 1296.3082973459811,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 239.49981689453125,
			"height": 50,
			"seed": 1109396222,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "mAerwjBDqASqLT81XjIr9",
					"type": "arrow"
				},
				{
					"id": "bFNMAn8SWga3X-RNUQqi3",
					"type": "arrow"
				}
			],
			"updated": 1698299542193,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Event Broker\n- SQS, SNS, EventBridge",
			"rawText": "Event Broker\n- SQS, SNS, EventBridge",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Event Broker\n- SQS, SNS, EventBridge",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 130,
			"versionNonce": 1907629730,
			"isDeleted": false,
			"id": "zkue0Pir",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -351.0387782858383,
			"y": 1298.6584188943343,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 151.71990966796875,
			"height": 50,
			"seed": 2038484770,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542193,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Event Publisher\n- API Gateway",
			"rawText": "Event Publisher\n- API Gateway",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Event Publisher\n- API Gateway",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 99,
			"versionNonce": 1243354238,
			"isDeleted": false,
			"id": "MIYGujI0",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 271.1203765475279,
			"y": 1299.1557701987535,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 153.2398681640625,
			"height": 50,
			"seed": 1099855486,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "bFNMAn8SWga3X-RNUQqi3",
					"type": "arrow"
				}
			],
			"updated": 1698299542193,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Event Consumer\n- lambda",
			"rawText": "Event Consumer\n- lambda",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Event Consumer\n- lambda",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 44,
			"versionNonce": 79428194,
			"isDeleted": false,
			"id": "mAerwjBDqASqLT81XjIr9",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -179.9568975203058,
			"y": 1319.511867406111,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 82.58836852318029,
			"height": 2.9779042403235962,
			"seed": 1599912354,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698299542193,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "kH7dQxQE",
				"focus": -0.19602601450017124,
				"gap": 6.870784040474405
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
					82.58836852318029,
					2.9779042403235962
				]
			]
		},
		{
			"type": "arrow",
			"version": 44,
			"versionNonce": 820040894,
			"isDeleted": false,
			"id": "bFNMAn8SWga3X-RNUQqi3",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 157.14244128008693,
			"y": 1318.0909237890082,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 101.67126508362082,
			"height": 3.3454395547269087,
			"seed": 270443646,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698299542193,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "kH7dQxQE",
				"focus": -0.2565810977372119,
				"gap": 8.140369342206782
			},
			"endBinding": {
				"elementId": "MIYGujI0",
				"focus": -0.0075097304152586765,
				"gap": 12.306670183820131
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
					101.67126508362082,
					3.3454395547269087
				]
			]
		},
		{
			"type": "text",
			"version": 174,
			"versionNonce": 1775394338,
			"isDeleted": false,
			"id": "79wYeWri",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -356.7974315408002,
			"y": 1392.8325279775352,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 395.15972900390625,
			"height": 50,
			"seed": 197471970,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542193,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Aws Lambda\n대표적인 서버리스 컴퓨팅 시스템이다. ex. ec2",
			"rawText": "Aws Lambda\n대표적인 서버리스 컴퓨팅 시스템이다. ex. ec2",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Aws Lambda\n대표적인 서버리스 컴퓨팅 시스템이다. ex. ec2",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 475,
			"versionNonce": 430148862,
			"isDeleted": false,
			"id": "g0W4mudJ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -342.84552330945456,
			"y": 2013.995863773796,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 159.75987243652344,
			"height": 200,
			"seed": 214518910,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "r8r8gC1BGxA8ex3w55m53",
					"type": "arrow"
				}
			],
			"updated": 1698299542193,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Event Source\n- 데이터 상태 변화\n(dynamo db, rds)\n- 엔드포인트 요청\n(api gateway)\n- 리소스 상태 변화\n(s3)\n- etc",
			"rawText": "Event Source\n- 데이터 상태 변화\n(dynamo db, rds)\n- 엔드포인트 요청\n(api gateway)\n- 리소스 상태 변화\n(s3)\n- etc",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Event Source\n- 데이터 상태 변화\n(dynamo db, rds)\n- 엔드포인트 요청\n(api gateway)\n- 리소스 상태 변화\n(s3)\n- etc",
			"lineHeight": 1.25,
			"baseline": 193
		},
		{
			"type": "text",
			"version": 280,
			"versionNonce": 1843808738,
			"isDeleted": false,
			"id": "OEKRrZrn",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -34.43260436045421,
			"y": 2088.7294393553207,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 119.01992797851562,
			"height": 50,
			"seed": 1932409854,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "r8r8gC1BGxA8ex3w55m53",
					"type": "arrow"
				},
				{
					"id": "mNhM1Hcnz01UQjXUOZA3W",
					"type": "arrow"
				}
			],
			"updated": 1698299542193,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Aws Lambda\n(function)",
			"rawText": "Aws Lambda\n(function)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Aws Lambda\n(function)",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 1126,
			"versionNonce": 31800638,
			"isDeleted": false,
			"id": "r8r8gC1BGxA8ex3w55m53",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -172.14119951468984,
			"y": 2113.6272991081555,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 130.60098308986784,
			"height": 1.048259011905884,
			"seed": 285792610,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698299542193,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "g0W4mudJ",
				"focus": -0.010905676340149223,
				"gap": 10.944451358241281
			},
			"endBinding": {
				"elementId": "OEKRrZrn",
				"focus": -0.058122300092099614,
				"gap": 7.1076120643678
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
					130.60098308986784,
					1.048259011905884
				]
			]
		},
		{
			"type": "text",
			"version": 173,
			"versionNonce": 1745272226,
			"isDeleted": false,
			"id": "ifVouPbx",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -152.22622563731323,
			"y": 2074.210347446959,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 74.919921875,
			"height": 25,
			"seed": 500967422,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542193,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "request",
			"rawText": "request",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "request",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 249,
			"versionNonce": 252110206,
			"isDeleted": false,
			"id": "AOQvzZbyXin0-6cfRrAoY",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 219.08132868497665,
			"y": 2030.1543636595989,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 105,
			"height": 144,
			"seed": 1850568226,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "sQsQkIpe"
				},
				{
					"id": "mNhM1Hcnz01UQjXUOZA3W",
					"type": "arrow"
				}
			],
			"updated": 1698299542193,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 218,
			"versionNonce": 1969404258,
			"isDeleted": false,
			"id": "sQsQkIpe",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 233.0413735458165,
			"y": 2077.154363659599,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 77.07991027832031,
			"height": 50,
			"seed": 1713994046,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542193,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "aws \nservices",
			"rawText": "aws services",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "AOQvzZbyXin0-6cfRrAoY",
			"originalText": "aws services",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 518,
			"versionNonce": 1078883256,
			"isDeleted": false,
			"id": "mNhM1Hcnz01UQjXUOZA3W",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 183.96272434106874,
			"y": 2106.1615099986147,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 32.32045640989253,
			"height": 1.1316534660491016,
			"seed": 1210068258,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698365022471,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "yz7Eq7uL",
				"gap": 7.762439268601014,
				"focus": 1.435881509841189
			},
			"endBinding": {
				"elementId": "AOQvzZbyXin0-6cfRrAoY",
				"gap": 2.7981479340153896,
				"focus": -0.012721180103528674
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
					32.32045640989253,
					-1.1316534660491016
				]
			]
		},
		{
			"type": "text",
			"version": 217,
			"versionNonce": 893992226,
			"isDeleted": false,
			"id": "yz7Eq7uL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 103.93050693540374,
			"y": 2075.3202859996686,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 74.919921875,
			"height": 25,
			"seed": 560362302,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "mNhM1Hcnz01UQjXUOZA3W",
					"type": "arrow"
				}
			],
			"updated": 1698299542194,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "request",
			"rawText": "request",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "request",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 561,
			"versionNonce": 214834686,
			"isDeleted": false,
			"id": "85btoOSz",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -36.5676650239493,
			"y": 2210.5092067019127,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 346.6197509765625,
			"height": 125,
			"seed": 1177993342,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542194,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "must config iam roles\nshort running process에 적합하다.\n- memory 사용 시간에 따라 과금이 된다.\n- timeout이 존재한다.\nsecurity group을 정의할 수 있다.",
			"rawText": "must config iam roles\nshort running process에 적합하다.\n- memory 사용 시간에 따라 과금이 된다.\n- timeout이 존재한다.\nsecurity group을 정의할 수 있다.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "must config iam roles\nshort running process에 적합하다.\n- memory 사용 시간에 따라 과금이 된다.\n- timeout이 존재한다.\nsecurity group을 정의할 수 있다.",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "line",
			"version": 240,
			"versionNonce": 86591714,
			"isDeleted": false,
			"id": "Z274qWgHPRkzX6Fy8cijl",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 13.917123431468326,
			"y": 2141.4701797543325,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 2.445132204393417,
			"height": 73.05379644942218,
			"seed": 259573410,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698299542194,
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
					2.445132204393417,
					73.05379644942218
				]
			]
		},
		{
			"type": "text",
			"version": 349,
			"versionNonce": 865447486,
			"isDeleted": false,
			"id": "MKi8TAZR",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -338.3295335279882,
			"y": 2391.62236118,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 505.1396484375,
			"height": 100,
			"seed": 216856418,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542194,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "concurrency:\nlambda가 동시에 처리할 수 있는 request의 개수\n\ndefault value: 1,000 for each region, each account",
			"rawText": "concurrency:\nlambda가 동시에 처리할 수 있는 request의 개수\n\ndefault value: 1,000 for each region, each account",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "concurrency:\nlambda가 동시에 처리할 수 있는 request의 개수\n\ndefault value: 1,000 for each region, each account",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "text",
			"version": 301,
			"versionNonce": 1016192162,
			"isDeleted": false,
			"id": "pduLXUZz",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -341.0678579964444,
			"y": 2533.1776686274,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 782.1594848632812,
			"height": 50,
			"seed": 1949131582,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542194,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Labmda Layers\n각각의 Labmda 함수가 동일한 코드를 사용하고 있다면 layer를 만들어서 공통화 할 수 있다.",
			"rawText": "Labmda Layers\n각각의 Labmda 함수가 동일한 코드를 사용하고 있다면 layer를 만들어서 공통화 할 수 있다.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Labmda Layers\n각각의 Labmda 함수가 동일한 코드를 사용하고 있다면 layer를 만들어서 공통화 할 수 있다.",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 476,
			"versionNonce": 1937847934,
			"isDeleted": false,
			"id": "ipMuKWwT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -344.5104207177121,
			"y": 2619.3066906727013,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 446.2197265625,
			"height": 125,
			"seed": 576916706,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542194,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Container Image Support for Lambda\n- Dockerfile을 통한 간편한 종속성 관리\n- 기존 Container를 다루던 방식과 동일한 작업 방식\n- 최대 10GB의 컨테이너 이미지 지원\n- AWS에서 만든 이미지를 상속해야한다.",
			"rawText": "Container Image Support for Lambda\n- Dockerfile을 통한 간편한 종속성 관리\n- 기존 Container를 다루던 방식과 동일한 작업 방식\n- 최대 10GB의 컨테이너 이미지 지원\n- AWS에서 만든 이미지를 상속해야한다.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Container Image Support for Lambda\n- Dockerfile을 통한 간편한 종속성 관리\n- 기존 Container를 다루던 방식과 동일한 작업 방식\n- 최대 10GB의 컨테이너 이미지 지원\n- AWS에서 만든 이미지를 상속해야한다.",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "text",
			"version": 166,
			"versionNonce": 1764882530,
			"isDeleted": false,
			"id": "6DFc4jnS",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 585.6609911582146,
			"y": 1292.6053403626638,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 842.759521484375,
			"height": 50,
			"seed": 364191138,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299542194,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "API Gateway\nAPI를 손쉽게 생성, 게시, 유지 관리, 모니터링 및 보안 유지를 할 수 있도록 하는 완전관리형 서비스",
			"rawText": "API Gateway\nAPI를 손쉽게 생성, 게시, 유지 관리, 모니터링 및 보안 유지를 할 수 있도록 하는 완전관리형 서비스",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "API Gateway\nAPI를 손쉽게 생성, 게시, 유지 관리, 모니터링 및 보안 유지를 할 수 있도록 하는 완전관리형 서비스",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "embeddable",
			"version": 447,
			"versionNonce": 56841144,
			"isDeleted": false,
			"id": "OykiHjmjyP-ryvwyEd-Vz",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 581.6734715201753,
			"y": 1357.5733272086961,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 844.3956228851632,
			"height": 393.300865602749,
			"seed": 643977250,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1698365022363,
			"link": "https://docs.aws.amazon.com/apigateway/latest/developerguide/welcome.html",
			"locked": false,
			"validated": true
		},
		{
			"type": "embeddable",
			"version": 245,
			"versionNonce": 1442243528,
			"isDeleted": false,
			"id": "WVFiDn2zrxSgXsUY5PLkg",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -361.359991173307,
			"y": 1475.7334005231,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 773.2927401960137,
			"height": 478.6633056091651,
			"seed": 794900642,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1698365022363,
			"link": "https://docs.aws.amazon.com/lambda/latest/dg/welcome.html",
			"locked": false,
			"validated": true
		},
		{
			"type": "text",
			"version": 100,
			"versionNonce": 1700882302,
			"isDeleted": false,
			"id": "8wdPSaZh",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 594.5631849824803,
			"y": 1841.3174965869925,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 333.43975830078125,
			"height": 50,
			"seed": 1062077630,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299636432,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "HTTP API VS REST API\nREST API에서만 caching을 지원한다.",
			"rawText": "HTTP API VS REST API\nREST API에서만 caching을 지원한다.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "HTTP API VS REST API\nREST API에서만 caching을 지원한다.",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "embeddable",
			"version": 280,
			"versionNonce": 1412439224,
			"isDeleted": false,
			"id": "xZ_ixQEpFTKsRYuIk22GR",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 582.3898831233039,
			"y": 1911.1037197649189,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 823.696334404113,
			"height": 687.6069651951093,
			"seed": 1845073506,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1698365022363,
			"link": "https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api-vs-rest.html",
			"locked": false,
			"validated": true
		},
		{
			"type": "text",
			"version": 19,
			"versionNonce": 2091302974,
			"isDeleted": false,
			"id": "0DgRgzGM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 635.6587912146131,
			"y": 2675.409793784496,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 212.11985778808594,
			"height": 25,
			"seed": 1822231394,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299883842,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "API Gateway Stages",
			"rawText": "API Gateway Stages",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "API Gateway Stages",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 42,
			"versionNonce": 502964350,
			"isDeleted": false,
			"id": "SUkPxgBrfbmBUxuQ7894Q",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 650.1787266373583,
			"y": 2733.4999368854815,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 177,
			"height": 48,
			"seed": 908995106,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "9jCFQEZS"
				},
				{
					"id": "6YBHHMYFBJDSqA1dW9gr1",
					"type": "arrow"
				}
			],
			"updated": 1698299969278,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 13,
			"versionNonce": 655414690,
			"isDeleted": false,
			"id": "9jCFQEZS",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 678.4587711930224,
			"y": 2744.9999368854815,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 120.43991088867188,
			"height": 25,
			"seed": 672809470,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299901937,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "alias = prod",
			"rawText": "alias = prod",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "SUkPxgBrfbmBUxuQ7894Q",
			"originalText": "alias = prod",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 95,
			"versionNonce": 1841154722,
			"isDeleted": false,
			"id": "FkFo4quJnUQVnIUgFUGjP",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 650.9783541460826,
			"y": 2799.0497109098815,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 178,
			"height": 53,
			"seed": 828551870,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "euiHsmhW"
				},
				{
					"id": "Ay6ihjK0oSbKn7uevk9LT",
					"type": "arrow"
				}
			],
			"updated": 1698299971142,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 15,
			"versionNonce": 234577122,
			"isDeleted": false,
			"id": "euiHsmhW",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 677.3483950396372,
			"y": 2813.0497109098815,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 125.25991821289062,
			"height": 25,
			"seed": 1387402814,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299906171,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "alias = beta",
			"rawText": "alias = beta",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "FkFo4quJnUQVnIUgFUGjP",
			"originalText": "alias = beta",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 138,
			"versionNonce": 1188891006,
			"isDeleted": false,
			"id": "f2yykmb5g5Uwi306svIpK",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 649.989769516244,
			"y": 2874.7983835670366,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 185,
			"height": 41,
			"seed": 782440894,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "pIv0QG5R"
				},
				{
					"id": "9LfSY3P19wBEaMECu5790",
					"type": "arrow"
				}
			],
			"updated": 1698299973692,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 51,
			"versionNonce": 467757858,
			"isDeleted": false,
			"id": "pIv0QG5R",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 686.3398061373377,
			"y": 2882.7983835670366,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 112.2999267578125,
			"height": 25,
			"seed": 2017349858,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299920225,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "alias = dev",
			"rawText": "alias = dev",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "f2yykmb5g5Uwi306svIpK",
			"originalText": "alias = dev",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 50,
			"versionNonce": 42654306,
			"isDeleted": false,
			"id": "k8vFRaDxZFnqxFbQi8mDq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 919.2051726572017,
			"y": 2748.3087156102642,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 404.77308012119465,
			"height": 311.1799359368456,
			"seed": 1098287778,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1698299925441,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 29,
			"versionNonce": 2125386338,
			"isDeleted": false,
			"id": "39CWodn5",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 940.9255218045444,
			"y": 2717.5209192361544,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 66.13995361328125,
			"height": 25,
			"seed": 763177442,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299929819,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "lambda",
			"rawText": "lambda",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "lambda",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 66,
			"versionNonce": 456067426,
			"isDeleted": false,
			"id": "HRWbF1UizHF6ddtYEj_B2",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 946.6921082959575,
			"y": 2832.585443978751,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 93,
			"height": 41,
			"seed": 2063802850,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "vZFFUHRS"
				},
				{
					"id": "GHk6siaucT4fFF8VDuwoH",
					"type": "arrow"
				},
				{
					"id": "6YBHHMYFBJDSqA1dW9gr1",
					"type": "arrow"
				},
				{
					"id": "b1tuH5ewzS503rsDlAB8v",
					"type": "arrow"
				}
			],
			"updated": 1698300535667,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 6,
			"versionNonce": 1673861090,
			"isDeleted": false,
			"id": "vZFFUHRS",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 972.7321320996684,
			"y": 2840.585443978751,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 40.919952392578125,
			"height": 25,
			"seed": 739783458,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698300535670,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "prod",
			"rawText": "prod",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "HRWbF1UizHF6ddtYEj_B2",
			"originalText": "prod",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 37,
			"versionNonce": 1695993250,
			"isDeleted": false,
			"id": "c0G_kcYaF2-cGlvKjegbU",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 947.0463340692272,
			"y": 2894.8631911417074,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 103,
			"height": 46,
			"seed": 286823138,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "a7PSDRLt"
				},
				{
					"id": "FYMnw_HNb21YYnhB6y8gr",
					"type": "arrow"
				},
				{
					"id": "SDE6959wfqQpsmu63-iV6",
					"type": "arrow"
				}
			],
			"updated": 1698299976075,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 6,
			"versionNonce": 40952738,
			"isDeleted": false,
			"id": "a7PSDRLt",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 975.6763542108288,
			"y": 2905.3631911417074,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 45.739959716796875,
			"height": 25,
			"seed": 636681442,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299959738,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "beta",
			"rawText": "beta",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "c0G_kcYaF2-cGlvKjegbU",
			"originalText": "beta",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 51,
			"versionNonce": 1949218786,
			"isDeleted": false,
			"id": "ATOXBODJ8IsDxHRhpEtGy",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 959.5148746099467,
			"y": 2964.106611661263,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 95,
			"height": 44,
			"seed": 1371179746,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "mSHB6xq4"
				},
				{
					"id": "EdrrEwefvPicAXgPRl2vV",
					"type": "arrow"
				},
				{
					"id": "9LfSY3P19wBEaMECu5790",
					"type": "arrow"
				},
				{
					"id": "TsXh3karJ39jxddALKNCc",
					"type": "arrow"
				}
			],
			"updated": 1698299981207,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 4,
			"versionNonce": 623195518,
			"isDeleted": false,
			"id": "mSHB6xq4",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 990.6248904790873,
			"y": 2973.606611661263,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 32.77996826171875,
			"height": 25,
			"seed": 391171746,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698299943725,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "dev",
			"rawText": "dev",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "ATOXBODJ8IsDxHRhpEtGy",
			"originalText": "dev",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 45,
			"versionNonce": 893510050,
			"isDeleted": false,
			"id": "mOFrPLZMGRpPrGna5lrm8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1174.662830524137,
			"y": 2788.104068542537,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 107.98686820570356,
			"height": 21.915991998118443,
			"seed": 1988005026,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1698299947210,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 72,
			"versionNonce": 30685858,
			"isDeleted": false,
			"id": "t670wUMEpxjP9eLx1B4Ok",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1176.0163596346058,
			"y": 2818.2510347625757,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 107.98686820570356,
			"height": 21.915991998118443,
			"seed": 792666558,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1698299949274,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 114,
			"versionNonce": 451389282,
			"isDeleted": false,
			"id": "muMxF1DDB4UPTbLL99bDf",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1177.4457502586401,
			"y": 2848.6195964564527,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 107.98686820570356,
			"height": 21.915991998118443,
			"seed": 228293154,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "FYMnw_HNb21YYnhB6y8gr",
					"type": "arrow"
				},
				{
					"id": "EdrrEwefvPicAXgPRl2vV",
					"type": "arrow"
				},
				{
					"id": "TsXh3karJ39jxddALKNCc",
					"type": "arrow"
				}
			],
			"updated": 1698299981207,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 112,
			"versionNonce": 429215010,
			"isDeleted": false,
			"id": "6dGB4CkAabLD9uF7oAMHC",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1178.2203362392625,
			"y": 2879.5631085689347,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 107.98686820570356,
			"height": 21.915991998118443,
			"seed": 1789508030,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "SDE6959wfqQpsmu63-iV6",
					"type": "arrow"
				}
			],
			"updated": 1698299976075,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 70,
			"versionNonce": 1147641662,
			"isDeleted": false,
			"id": "2xrETmtpCDetnjTWvGOnh",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1178.7593522567058,
			"y": 2912.898254714369,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 107.98686820570356,
			"height": 21.915991998118443,
			"seed": 1262646370,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "b1tuH5ewzS503rsDlAB8v",
					"type": "arrow"
				}
			],
			"updated": 1698299978342,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 57,
			"versionNonce": 149944,
			"isDeleted": false,
			"id": "GHk6siaucT4fFF8VDuwoH",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1046.8162166090801,
			"y": 2853.712299643481,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 128.0462494770727,
			"height": 53.97347054665033,
			"seed": 492420578,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698365022472,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "HRWbF1UizHF6ddtYEj_B2",
				"gap": 7.124108313122463,
				"focus": 0.5793010985385038
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					128.0462494770727,
					-53.97347054665033
				]
			]
		},
		{
			"type": "arrow",
			"version": 72,
			"versionNonce": 2019401656,
			"isDeleted": false,
			"id": "FYMnw_HNb21YYnhB6y8gr",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1061.2299041866363,
			"y": 2914.9205629575918,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 105.2890904866972,
			"height": 74.98373810002158,
			"seed": 1896185790,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698365022472,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "c0G_kcYaF2-cGlvKjegbU",
				"gap": 11.18357011740909,
				"focus": 0.6987432812280168
			},
			"endBinding": {
				"elementId": "muMxF1DDB4UPTbLL99bDf",
				"gap": 13.956522140540073,
				"focus": 1.3332182167353999
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
					105.2890904866972,
					-74.98373810002158
				]
			]
		},
		{
			"type": "arrow",
			"version": 73,
			"versionNonce": 387187640,
			"isDeleted": false,
			"id": "EdrrEwefvPicAXgPRl2vV",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1056.9856521381757,
			"y": 2989.712029911272,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 118.49568419022694,
			"height": 132.40229744026283,
			"seed": 1391566306,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698365022473,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ATOXBODJ8IsDxHRhpEtGy",
				"gap": 2.470777528229064,
				"focus": 0.7917559604730204
			},
			"endBinding": {
				"elementId": "muMxF1DDB4UPTbLL99bDf",
				"gap": 1.9644139302374697,
				"focus": 0.9088882878556273
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
					118.49568419022694,
					-132.40229744026283
				]
			]
		},
		{
			"type": "arrow",
			"version": 64,
			"versionNonce": 810892216,
			"isDeleted": false,
			"id": "6YBHHMYFBJDSqA1dW9gr1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 831.1858533643401,
			"y": 2762.7623303002238,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 112.59046426579289,
			"height": 96.16045751187494,
			"seed": 721707042,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698365022472,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "SUkPxgBrfbmBUxuQ7894Q",
				"gap": 4.007126726981824,
				"focus": -0.7405241802394813
			},
			"endBinding": {
				"elementId": "HRWbF1UizHF6ddtYEj_B2",
				"gap": 2.915790665824545,
				"focus": -0.7978496642947152
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
					112.59046426579289,
					96.16045751187494
				]
			]
		},
		{
			"type": "arrow",
			"version": 31,
			"versionNonce": 782855864,
			"isDeleted": false,
			"id": "Ay6ihjK0oSbKn7uevk9LT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 831.8246871627913,
			"y": 2821.5350397577395,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 116.29969300805067,
			"height": 98.08095161846859,
			"seed": 994003262,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698365022471,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "FkFo4quJnUQVnIUgFUGjP",
				"gap": 2.8463330167087406,
				"focus": -0.8022320881661373
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					116.29969300805067,
					98.08095161846859
				]
			]
		},
		{
			"type": "arrow",
			"version": 77,
			"versionNonce": 1707111864,
			"isDeleted": false,
			"id": "9LfSY3P19wBEaMECu5790",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 839.9059347131997,
			"y": 2903.549321345159,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 118.60893989674696,
			"height": 82.71663619706896,
			"seed": 716187234,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698365022473,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "f2yykmb5g5Uwi306svIpK",
				"gap": 4.916165196955717,
				"focus": -0.7021186665500803
			},
			"endBinding": {
				"elementId": "ATOXBODJ8IsDxHRhpEtGy",
				"gap": 1,
				"focus": -0.6164557011126647
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
					118.60893989674696,
					82.71663619706896
				]
			]
		},
		{
			"type": "arrow",
			"version": 50,
			"versionNonce": 1045631416,
			"isDeleted": false,
			"id": "SDE6959wfqQpsmu63-iV6",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1063.0505805122223,
			"y": 2922.1353921688506,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 114.11967267083583,
			"height": 28.66367399426008,
			"seed": 1475236414,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698365022473,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "c0G_kcYaF2-cGlvKjegbU",
				"gap": 13.004246442995054,
				"focus": 0.5697414771058555
			},
			"endBinding": {
				"elementId": "6dGB4CkAabLD9uF7oAMHC",
				"gap": 1.0500830562043575,
				"focus": 0.44351307936248685
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
					114.11967267083583,
					-28.66367399426008
				]
			]
		},
		{
			"type": "arrow",
			"version": 72,
			"versionNonce": 437497272,
			"isDeleted": false,
			"id": "b1tuH5ewzS503rsDlAB8v",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1048.301505190479,
			"y": 2856.68686951752,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 122.66008201388104,
			"height": 66.6223797559851,
			"seed": 628316386,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698365022472,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "HRWbF1UizHF6ddtYEj_B2",
				"gap": 8.60939689452158,
				"focus": -0.5754626161977011
			},
			"endBinding": {
				"elementId": "2xrETmtpCDetnjTWvGOnh",
				"gap": 7.797765052345767,
				"focus": -0.819541028165661
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
					122.66008201388104,
					66.6223797559851
				]
			]
		},
		{
			"type": "arrow",
			"version": 68,
			"versionNonce": 1165518776,
			"isDeleted": false,
			"id": "TsXh3karJ39jxddALKNCc",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1059.8963386323694,
			"y": 2978.5763582620184,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 97.83006812280769,
			"height": 133.95881299577923,
			"seed": 1458374526,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698365022473,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ATOXBODJ8IsDxHRhpEtGy",
				"gap": 5.381464022422733,
				"focus": 0.7453934839005844
			},
			"endBinding": {
				"elementId": "muMxF1DDB4UPTbLL99bDf",
				"gap": 14.385738598874013,
				"focus": 1.3652174348810593
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
					97.83006812280769,
					-133.95881299577923
				]
			]
		},
		{
			"type": "text",
			"version": 80,
			"versionNonce": 1386776482,
			"isDeleted": false,
			"id": "PDXcDw7l",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1574.353995136868,
			"y": 1288.8764586119855,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 38.41996765136719,
			"height": 25,
			"seed": 193601598,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698300087838,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "SQS",
			"rawText": "SQS",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "SQS",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "embeddable",
			"version": 100,
			"versionNonce": 1542925000,
			"isDeleted": false,
			"id": "ZsY9R3_69BZf3-jfzVNem",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1560.9946793943157,
			"y": 1324.7601113235085,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 560,
			"height": 312.13535471921,
			"seed": 341663038,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1698365022363,
			"link": "https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html",
			"locked": false,
			"validated": true
		},
		{
			"type": "embeddable",
			"version": 189,
			"versionNonce": 1652278712,
			"isDeleted": false,
			"id": "xKEm5Vh8jPGw3e-GToygn",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2170.3847050608065,
			"y": 1327.2688846945557,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 560,
			"height": 370.3677692804238,
			"seed": 182207394,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1698365022363,
			"link": "https://docs.aws.amazon.com/sns/latest/dg/welcome.html",
			"locked": false,
			"validated": true
		},
		{
			"type": "text",
			"version": 23,
			"versionNonce": 703450338,
			"isDeleted": false,
			"id": "M6I8D6vt",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2190.0218067349483,
			"y": 1296.0867435104192,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 37.19996643066406,
			"height": 25,
			"seed": 602362594,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698300093174,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "SNS",
			"rawText": "SNS",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "SNS",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "line",
			"version": 192,
			"versionNonce": 157790370,
			"isDeleted": false,
			"id": "IJQbvr3hUItyel6b6cN_A",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1577.2451321010124,
			"y": 1723.459993853948,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1157.0127243702611,
			"height": 1.911817965493583,
			"seed": 1101364322,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1698300110223,
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
					1157.0127243702611,
					-1.911817965493583
				]
			]
		},
		{
			"type": "text",
			"version": 548,
			"versionNonce": 1797887906,
			"isDeleted": false,
			"id": "dFctUOwD",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2193.080715479739,
			"y": 1772.6522406068993,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 592.2994995117188,
			"height": 400,
			"seed": 984292322,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698300361353,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "- 완전 관리형 게시/구독 서비스\n- Push 베이스\n- publisher는 Topic에 메시지를 publish\n- multiple subscribers\n- subscriber는 메시지를 filtering하여 원하는 메시지만 받을 수 있다.\n\nTopic Types\nStandard, FIFO\n\nFIFO: 정확히 1회 메시지 전송\n- SQS만 같이 사용가능\n\nStandard: 최소 1회 메시지 전송\n\nfire-and-forget 메시지 전송 후 이벤트 삭제\n",
			"rawText": "- 완전 관리형 게시/구독 서비스\n- Push 베이스\n- publisher는 Topic에 메시지를 publish\n- multiple subscribers\n- subscriber는 메시지를 filtering하여 원하는 메시지만 받을 수 있다.\n\nTopic Types\nStandard, FIFO\n\nFIFO: 정확히 1회 메시지 전송\n- SQS만 같이 사용가능\n\nStandard: 최소 1회 메시지 전송\n\nfire-and-forget 메시지 전송 후 이벤트 삭제\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "- 완전 관리형 게시/구독 서비스\n- Push 베이스\n- publisher는 Topic에 메시지를 publish\n- multiple subscribers\n- subscriber는 메시지를 filtering하여 원하는 메시지만 받을 수 있다.\n\nTopic Types\nStandard, FIFO\n\nFIFO: 정확히 1회 메시지 전송\n- SQS만 같이 사용가능\n\nStandard: 최소 1회 메시지 전송\n\nfire-and-forget 메시지 전송 후 이벤트 삭제\n",
			"lineHeight": 1.25,
			"baseline": 393
		},
		{
			"type": "text",
			"version": 401,
			"versionNonce": 1282974718,
			"isDeleted": false,
			"id": "oixiyS7B",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1607.3387075456135,
			"y": 1773.9866115134291,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 404.999755859375,
			"height": 325,
			"seed": 1109822434,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698300447314,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "- 완전 관리형 메시지 대기열\n- pull 베이스\n- producer는 queue에 메시지 전송, \nconsumer는 polling으로 메시지 취득\n\nTopic Types\nStandard, FIFO\n\nSQS는 메시지를 일괄 처리한다.\n- processing event's type batch\n\nbatch size: 일괄 처리한 메시지의 수\nbatch window: 일괄 처리를 위해 대기하는 시간",
			"rawText": "- 완전 관리형 메시지 대기열\n- pull 베이스\n- producer는 queue에 메시지 전송, \nconsumer는 polling으로 메시지 취득\n\nTopic Types\nStandard, FIFO\n\nSQS는 메시지를 일괄 처리한다.\n- processing event's type batch\n\nbatch size: 일괄 처리한 메시지의 수\nbatch window: 일괄 처리를 위해 대기하는 시간",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "- 완전 관리형 메시지 대기열\n- pull 베이스\n- producer는 queue에 메시지 전송, \nconsumer는 polling으로 메시지 취득\n\nTopic Types\nStandard, FIFO\n\nSQS는 메시지를 일괄 처리한다.\n- processing event's type batch\n\nbatch size: 일괄 처리한 메시지의 수\nbatch window: 일괄 처리를 위해 대기하는 시간",
			"lineHeight": 1.25,
			"baseline": 318
		},
		{
			"type": "text",
			"version": 174,
			"versionNonce": 160739582,
			"isDeleted": false,
			"id": "mbRKGbfM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2893.3697683662367,
			"y": 1287.5811918052884,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 368.23974609375,
			"height": 100,
			"seed": 646277154,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1698300788319,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "EventBridge\n\n- event: 시스템에 상태 변화가 있다는 신호\n- event bus: config rule and target",
			"rawText": "EventBridge\n\n- event: 시스템에 상태 변화가 있다는 신호\n- event bus: config rule and target",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "EventBridge\n\n- event: 시스템에 상태 변화가 있다는 신호\n- event bus: config rule and target",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"id": "cUSVRSKc",
			"type": "text",
			"x": -11.780197783042638,
			"y": 731.1157005132129,
			"width": 10,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 157014456,
			"version": 39,
			"versionNonce": 1581612216,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1698365052982,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
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
		"scrollX": -127.70416494943547,
		"scrollY": 1269.0584494862478,
		"zoom": {
			"value": 0.35000000000000014
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