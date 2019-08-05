---
title: ClientVersions 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions view는 다양 한 클라이언트 유형 및 데이터베이스에 기록 된 세션에 참가 한 버전에 대 한 정보를 저장 합니다. 뷰의 각 레코드는 하나의 클라이언트 버전을 나타냅니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 845a6fdb88ba62273413d8e7ea50fb165f0f321c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196791"
---
# <a name="clientversions-view"></a>ClientVersions 보기
 
ClientVersions view는 다양 한 클라이언트 유형 및 데이터베이스에 기록 된 세션에 참가 한 버전에 대 한 정보를 저장 합니다. 뷰의 각 레코드는 하나의 클라이언트 버전을 나타냅니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
> [!NOTE]
> 특정 열에 여러 레코드가 있을 수 있습니다. 
  
|**열**|**데이터 형식**|**세부적인**|
|:-----|:-----|:-----|
|**#** <br/> |int  <br/> |이 클라이언트 유형 및 버전을 식별 하는 고유 번호입니다.  <br/> |
|**버전** <br/> |nvarchar (256)  <br/> |사용자 에이전트를 나타냅니다.  <br/> |
|**ClientType** <br/> |int  <br/> |클라이언트의 유형입니다.  <br/> |
|**ClientCategory** <br/> |nvarchar (64)  <br/> |클라이언트가 속한 범주 예를 들어 클라이언트 Conferencing_Attendant_ 1.0은 ClientCategory CA에 속합니다.  <br/> |
   

