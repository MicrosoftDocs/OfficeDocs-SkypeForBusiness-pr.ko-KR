---
title: VoIPDetails 보기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: VoIPDetails 보기에는 한 명 이상의 사용자가 VoIP 사용자인 피어 투 피어 세션에 대한 정보가 저장됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
ms.openlocfilehash: 9e8eeaa0e907496d03a4541792f6f100a9191324497ee7603a65ec5a71fba592
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351957"
---
# <a name="voipdetails-view"></a>VoIPDetails 보기
 
VoIPDetails 보기에는 한 명 이상의 사용자가 VoIP 사용자인 피어 투 피어 세션에 대한 정보가 저장됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
  
> [!NOTE]
> VoIPDetails 보기에는 [SessionDetails](sessiondetails-0.md) 보기의 모든 열과 아래에 나열된 열이 포함되어 있습니다.
  
|**열**|**데이터 형식**|**세부 정보**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar(450)  <br/> |세션을 시작한 사용자의 전화 URI입니다.  <br/> |
|**ToPhone** <br/> |nvarchar(450)  <br/> |세션에 참가한 사용자의 전화 URI입니다.  <br/> |
|**DisconnectedByUri** <br/> |nvarchar(450)  <br/> |세션 연결을 끊은 사용자의 URI입니다.  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar(256)  <br/> |세션 연결을 끊은 사용자의 URI 유형입니다. 자세한 내용은 [UriTypes 테이블을](uritypes.md) 참조하십시오. <br/> |
|**DisconnectedByTenant** <br/> |nvarchar(256)  <br/> |세션 연결을 끊은 사용자의 테넌트입니다.  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar(450)  <br/> |세션 연결을 끊은 사용자의 전화 URI입니다.  <br/> |
|**FromMediationServer** <br/> |nvarchar(256)  <br/> |세션을 시작한 사용자가 사용하는 중재 서버입니다.  <br/> |
|**ToMediationServer** <br/> |nvarchar(256)  <br/> |세션에 참가한 사용자가 사용하는 중재 서버입니다.  <br/> |
|**FromGateway** <br/> |nvarchar(256)  <br/> |세션을 시작한 사용자가 사용하는 게이트웨이입니다.  <br/> |
|**ToGateway** <br/> |nvarchar(256)  <br/> |세션에 참가한 사용자가 사용하는 게이트웨이입니다.  <br/> |
   

