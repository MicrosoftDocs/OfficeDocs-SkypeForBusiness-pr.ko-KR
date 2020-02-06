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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions view는 다양 한 클라이언트 유형 및 데이터베이스에 기록 된 세션에 참가 한 버전에 대 한 정보를 저장 합니다. 뷰의 각 레코드는 하나의 클라이언트 버전을 나타냅니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: d37e2a1599eaf8906d11fdb8faf545aa3447f00f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815416"
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
|**ClientCategory** <br/> |nvarchar (64)  <br/> |클라이언트가 속한 범주 예를 들어 클라이언트 Conferencing_Attendant_1 .0는 ClientCategory CA에 속합니다.  <br/> |
   

