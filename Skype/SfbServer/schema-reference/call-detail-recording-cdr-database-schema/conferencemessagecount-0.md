---
title: ConferenceMessageCount 보기
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
ms.localizationpriority: medium
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: ConferenceMessageCount 보기에는 사용자가 회의에 전송한 메시지 수에 대한 정보가 저장됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
ms.openlocfilehash: 5b4cadd741eae999a789a51c6adc0400cc8ce45f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593432"
---
# <a name="conferencemessagecount-view"></a>ConferenceMessageCount 보기
 
ConferenceMessageCount 보기에는 사용자가 회의에 전송한 메시지 수에 대한 정보가 저장됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
  
> [!NOTE]
> ConferenceMessageCount 보기에는 [ConferenceSessionDetails](conferencesessiondetails.md) 보기의 모든 열과 아래에 나열된 열이 포함되어 있습니다.
  
|**열**|**데이터 형식**|**세부 정보**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar(450)  <br/> |메시지를 보낸 사용자의 URI입니다.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |메시지를 보낸 사용자 URI의 형식입니다. 자세한 내용은 [UriTypes 테이블을](uritypes.md) 참조하십시오. <br/> |
|**UserTenant** <br/> |uniqueidentifier  <br/> |메시지를 보낸 사용자의 테넌트입니다. 자세한 내용은 [Tenants 테이블을](tenants.md) 참조하세요. <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |회의 세션 중 사용자가 보낸 메시지 수입니다.  <br/> |
   

