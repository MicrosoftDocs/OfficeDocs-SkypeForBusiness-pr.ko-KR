---
title: FocusJoinsAndLeaves 보기
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
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: FocusJoinsAndLeaves 보기에는 한 회의에 대한 참가 및 나가기 정보에 대한 정보가 저장됩니다. 각 회의는 사용자가 회의에 참가하고 회의에서 나설 때마다 작성된 레코드로 이 보기에 표시됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
ms.openlocfilehash: 102e520c9bfdb9988061db64dec621a8683b1b5e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628560"
---
# <a name="focusjoinsandleaves-view"></a>FocusJoinsAndLeaves 보기
 
FocusJoinsAndLeaves 보기에는 한 회의에 대한 참가 및 나가기 정보에 대한 정보가 저장됩니다. 각 회의는 사용자가 회의에 참가하고 회의에서 나설 때마다 작성된 레코드로 이 보기에 표시됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
  
|**열**|**데이터 형식**|**세부 정보**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |회의 인스턴스 시간입니다. SessionIdSeq와 함께 회의 인스턴스를 고유하게 식별하는 데 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Conferences](conferences.md) 테이블을 참조하십시오. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |전화 회의 인스턴스를 식별하기 위한 ID 번호입니다. SessionIdTime과 함께 회의 인스턴스를 고유하게 식별하는 데 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Conferences](conferences.md) 테이블을 참조하십시오. <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |회의 참가/나가기 정보가 캡처된 사용자의 URI입니다.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |회의 참가/나가기 정보가 캡처된 사용자의 URI 유형입니다. 자세한 내용은 [UriTypes 테이블을](uritypes.md) 참조하십시오. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |회의 참가/나가기 정보가 캡처된 사용자의 테넌트입니다. 자세한 내용은 [Tenants 테이블을](tenants.md) 참조하세요. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |회의 참가/나가기 정보가 캡처된 사용자의 고유 식별자입니다.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |회의 참가/나가기 정보를 캡처한 사용자가 사용한 클라이언트 버전입니다.  <br/> |
|**UserClientType** <br/> |int  <br/> |회의 참가/나가기 정보를 캡처한 사용자가 사용한 클라이언트입니다. 자세한 [내용은 UserAgentDef 테이블을](useragentdef.md) 참조합니다. <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |회의 참가/나가기 정보가 캡처된 사용자가 사용한 클라이언트 범주의 이름입니다.  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||
|**IsuserInternal** <br/> |bit  <br/> |사용자가 내부 사용자인지 여부를 나타내는 비트입니다.  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |세션 요청 시간입니다. SessionIdSeq와 함께 회의 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |사용자가 여러 컴퓨터 또는 장치에서 동시에 로그온되어 있는 경우 UserInstance를 사용하여 사용자/장치 조합을 고유하게 식별합니다.  <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |세션의 SIP 대화 ID입니다. 형식은 dialog;from-tag;to-tag입니다.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |사용자가 회의에 참가한 시간입니다.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |사용자가 회의에서 나간 시간입니다.  <br/> |
|**UserRole** <br/> |nvarchar(256)  <br/> |발표자 또는 참석자와 같은 회의에서 사용자의 역할  <br/> |
   

