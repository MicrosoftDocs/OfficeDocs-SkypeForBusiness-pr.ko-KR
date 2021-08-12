---
title: Conference 테이블
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
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: Conference 테이블은 지원 테이블입니다. 각 레코드는 하나의 회의 또는 피어-투-피어 세션을 나타냅니다.
ms.openlocfilehash: 6dfe60a28e8279f7b4c469c61cddc28912db261eedf4754588de4bd8f5852728
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309157"
---
# <a name="conference-table"></a>Conference 테이블
 
Conference 테이블은 지원 테이블입니다. 각 레코드는 하나의 회의 또는 피어-투-피어 세션을 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primary  <br/> |이 회의 레코드를 식별하는 고유 번호입니다.  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |unique  <br/> |항목이 회의인 경우 회의 URI이고 피어 투 피어 세션인 경우에는 DialogID입니다.  <br/> |
|**체크섬** <br/> |int  <br/> |index  <br/> |회의 URI의 체크섬입니다. 내부적으로 사용됩니다.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||내부 용도로만 사용됩니다.  <br/> |
   

