---
title: 추세 위치 비즈니스용 Skype 서버
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 61e2db3c-9f10-4411-8e7e-c6950faf8533
description: '요약: 추세 보고서에 대해 비즈니스용 Skype 서버.'
---

# <a name="location-trend-report-in-skype-for-business-server"></a>추세 위치 비즈니스용 Skype 서버
 
**요약:** 추세 보고서에 대해 비즈니스용 Skype 서버.
  
위치 추세 보고서는 네트워크 위치에 대한 통화 품질 추세 정보를 제공합니다.
  
## <a name="filters"></a>필터

필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 위치 추세 보고서에서는 액세스 유형(즉, 내부 액세스와 외부 액세스) 또는 유선/무선 네트워크 연결 등의 조건에 따라 반환되는 데이터를 필터링할 수 있습니다. 또한 데이터의 그룹 지정 방식도 선택할 수 있습니다. 이 경우 통화는 시간, 일 또는 주별로 그룹이 지정됩니다.
  
다음 표에서는 위치 추세 보고서에 사용할 수 있는 필터를 보여 줍니다. 
  
**위치 추세 보고서 필터**

|**이름**|**설명**|
|:-----|:-----|
|**시작** <br/> |시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.  <br/> 2015/7/7 오후 1:00  <br/> 시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.  <br/> 7/7/2015  <br/> 주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.  <br/> 7/3/2015  <br/> 주는 항상 일요일부터 토요일까지로 실행됩니다.  <br/> |
|**To** <br/> |시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.  <br/> 2015/7/7 오후 1:00  <br/> 종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.  <br/> 7/7/2015  <br/> 주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.  <br/> 7/3/2015  <br/> 주는 항상 일요일부터 토요일까지로 실행됩니다.  <br/> |
|**Interval** <br/> | 시간 간격입니다. 다음 중 하나를 선택합니다. <br/>  시간별(최대 25시간 표시 가능) <br/>  일별(최대 31일 표시 가능) <br/>  주별(최대 12주 표시 가능) <br/>  시작 및 종료 날짜가 선택한 간격에 허용되는 최대 값을 초과하면 시작 날짜로부터 최대한의 값 숫자만 표시됩니다. 예를 들어 일별 간격을 선택하고 시작 날짜가 1/1/2011이고 종료 날짜가 2/28/2011인 경우 8/1/2011 12:00 AM부터 9/1/2011 12:00 AM까지 총 31일의 데이터만 표시됩니다. <br/> |
|**액세스 유형** <br/> | 통화가 시도되었을 때 클라이언트가 내부 네트워크 또는 외부 네트워크에 로그온되어 있는지를 나타냅니다. 다음 중 하나를 선택합니다. <br/>  [모두] <br/>  내부 <br/>  외부 <br/> |
|**네트워크 유형** <br/> | 통화가 시도되었을 때 클라이언트가 연결된 네트워크의 유형을 나타냅니다. 다음 중 하나를 선택합니다. <br/>  [모두] <br/>  유선 <br/>  무선 <br/> |
|**VPN** <br/> | 통화가 시도되었을 때 외부 클라이언트가 VPN(가상 사설망) 연결을 사용 중이었는지를 나타냅니다. 다음 중 하나를 선택합니다. <br/>  [모두] <br/>  VPN <br/>  비 VPN <br/> |
   

