---
title: 하이브리드 연결 구성 | 2019 비즈니스용 Skype 서버 배포
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 비즈니스용 Skype 서버 하이브리드 연결을 구현하기 위한 Teams.
ms.openlocfilehash: 67caabe77afb9f06dcf28f47a93f8eef06c08de8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624570"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>사용자 및 사용자 비즈니스용 Skype 서버 하이브리드 Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

**요약:** 이 항목을 통해 사용자 및 사용자 간의 하이브리드 연결을 구성하는 비즈니스용 Skype 서버 Teams.  하이브리드 연결을 사용하면 사용자가 클라우드 서비스로 Teams 이동하고 사용자가 클라우드 서비스를 활용할 수 있습니다.
  
이 항목의 단계를 수행하기 전에 Plan [hybrid connectivity between 비즈니스용 Skype 서버 Teams.](plan-hybrid-connectivity.md)
  
다음 표에는 하이브리드 연결을 구성하는 데 비즈니스용 Skype 작업이 나열되어 있으며 자세한 내용은 관련 문서에 대한 링크를 제공합니다.
  
|단계|설명|
|:-----|:-----|
|사용자에 대한 테넌트 Microsoft 365   <br/> |자세한 내용은 Microsoft 365 에서 [Microsoft 365.](https://go.microsoft.com/fwlink/p/?LinkId=254980)  <br/> 환경을 사용할 준비가 되어 있는지 확인 Microsoft 365 시스템 요구 [사항을 참조하세요.](https://products.office.com/office-system-requirements)  <br/> 설정에 대한 자세한 내용은 Microsoft 365 [시작을 Microsoft 365.](https://go.microsoft.com/fwlink/p/?LinkId=254982)  <br/> |
|조직에 도메인을 Microsoft 365 소유권 확인  <br/> | 조직에 도메인을 추가하고 Microsoft 365 단계에 따라 도메인의 유효성을 검사해야 Microsoft 365. 이는 사용자가 도메인의 소유자를 확인하는 것입니다. <br/> 도메인을 Microsoft 365 조직에 추가하려면 [도메인을](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)추가하여 조직에 Microsoft 365.  <br/> |
|Active Directory 동기화 설정  <br/> |Active Directory 동기화는 사용자와 지속적으로 동기화되는 Microsoft 365. 이렇게 하면 각 사용자 계정 및 그룹의 동기화된 버전을 만들 수 있습니다.  <br/> <br> **중요:** 사용자가 조직에 이동되지 않은 경우에도 비즈니스용 Skype 및 온라인 배포 간에 조직의 모든 비즈니스용 Skype 사용자에 대한 AD 계정을 동기화해야 Teams. 모든 사용자를 동기화하지 않는 경우 조직의 온라인 사용자와의 통신이 예상대로 작동하지 않을 수 있습니다. 자세한 내용은 [Configure Azure AD 커넥트 for hybrid environments을 참조하세요.](configure-azure-ad-connect.md)         |
| 비즈니스용 Skype 하이브리드 구성하기 | 세 가지 기본 단계가 있습니다. <br><br> 1. 프레미스 환경과 페더미스를 연결하도록 Microsoft 365. <br> 2. 공유 SIP 주소 공간을 신뢰하고 Microsoft 365 SIP 주소 공간을 사용하도록 Microsoft 365.<br> 3. 조직에서 공유 SIP 주소 Microsoft 365 사용하도록 설정 <br><br> 또한, Exchange 있는 경우 Exchange 환경과 온라인 환경 간에 OAuth를 구성할 수 있습니다. <br> <br>자세한 내용은 [하이브리드 구성을 비즈니스용 Skype 참조하세요.](configure-federation-with-skype-for-business-online.md)
|파일럿 사용자 이동  <br/> |사용자 환경 준비 및 구성 단계를 완료한 후 Teams 사용자 이동을 시작할 수 Microsoft 365 있습니다. 자세한 내용은 [Move users from on premises to Teams.](move-users-from-on-premises-to-Teams.md)  <br/> |
