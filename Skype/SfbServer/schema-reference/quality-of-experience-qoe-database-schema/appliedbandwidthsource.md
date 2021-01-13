---
title: AppliedBandwidthSource 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: AppliedBandwidthSource 테이블은 지원 테이블입니다. 각 레코드는 하나의 소스를 나타냅니다.
ms.openlocfilehash: bf7e1be3b98bcd56fea16dbd7aa7171b056a7f3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831408"
---
# <a name="appliedbandwidthsource-table"></a>AppliedBandwidthSource 테이블
 
AppliedBandwidthSource 테이블은 지원 테이블입니다. 각 레코드는 하나의 소스를 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Primary  <br/> |원본을 식별하는 고유 번호입니다.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar(256)  <br/> |고유  <br/> |대역폭 한도가 부과되는 원본입니다. 대역폭 제한이 시작되는 위치(예: "정책 서버", "TURN Server" 또는 "Modality")를 설명합니다.  <br/> |
   

