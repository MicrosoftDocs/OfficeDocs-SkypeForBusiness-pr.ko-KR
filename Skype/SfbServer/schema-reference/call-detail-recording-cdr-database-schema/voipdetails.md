---
title: VoIPDetails 보기
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
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: VoIPDetails 보기는 사용자가 한 명 이상 VoIP 사용자 인 피어 투 피어 세션에 대 한 정보를 저장 합니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 4d3aec4c58c2cb11f21ec6403f7532bcde46b05e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814776"
---
# <a name="voipdetails-view"></a>VoIPDetails 보기
 
VoIPDetails 보기는 사용자가 한 명 이상 VoIP 사용자 인 피어 투 피어 세션에 대 한 정보를 저장 합니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
> [!NOTE]
> VoIPDetails 보기에는 [Sessiondetails 보기](sessiondetails-0.md) 의 모든 열과 아래에 나열 된 열이 포함 됩니다.
  
|**열**|**데이터 형식**|**세부적인**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar (450)  <br/> |세션을 시작한 사용자의 전화 URI입니다.  <br/> |
|**ToPhone** <br/> |nvarchar (450)  <br/> |세션에 참가 한 사용자의 전화 URI입니다.  <br/> |
|**DisconnectedByUri** <br/> |nvarchar (450)  <br/> |세션을 끊은 사용자의 URI입니다.  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar (256)  <br/> |세션을 끊은 사용자의 URI 유형입니다. 자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요. <br/> |
|**DisconnectedByTenant** <br/> |nvarchar (256)  <br/> |세션을 끊은 사용자의 테 넌 트입니다.  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar (450)  <br/> |세션을 끊은 사용자의 전화 URI입니다.  <br/> |
|**FromMediationServer** <br/> |nvarchar (256)  <br/> |세션을 시작한 사용자가 사용 하는 중재 서버입니다.  <br/> |
|**ToMediationServer** <br/> |nvarchar (256)  <br/> |세션에 참가 한 사용자가 사용 하는 중재 서버입니다.  <br/> |
|**FromGateway** <br/> |nvarchar (256)  <br/> |세션을 시작한 사용자가 사용 하는 게이트웨이  <br/> |
|**ToGateway** <br/> |nvarchar (256)  <br/> |세션에 참가 한 사용자가 사용 하는 게이트웨이  <br/> |
   

