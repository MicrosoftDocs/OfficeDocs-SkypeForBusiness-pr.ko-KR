---
title: 하이브리드 연결 구성 | 비즈니스용 Skype 서버 2019 연결 배포
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 비즈니스용 Skype 서버와 비즈니스용 Skype Online 간의 하이브리드 연결을 구현하기 위한 지침입니다.
ms.openlocfilehash: 3a68d39062387952b7a43bb22599265a69bf7a61
ms.sourcegitcommit: 80b66127b3415c99f9468625add6a8f2c36bca74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48376751"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>비즈니스용 Skype 서버 및 Office 365 간 하이브리드 연결 구성

**요약:** 이 항목을 읽고 비즈니스용 Skype 서버와 Teams 또는 비즈니스용 Skype Online 간에 하이브리드 연결을 구성하는 방법을 배워야 합니다.  하이브리드 연결을 사용하면 프레미스 사용자를 Teams 또는 비즈니스용 Skype Online으로 이동할 수 있으며 사용자가 클라우드 서비스를 활용할 수 있습니다.
  
이 항목의 단계를 수행하기 전에 비즈니스용 Skype 서버와 [Office 365](plan-hybrid-connectivity.md)간의 하이브리드 연결 계획이 있어야 합니다.
  
다음 표에서는 비즈니스용 Skype 하이브리드 연결을 구성하는 데 필요한 작업을 나열하고 자세한 내용은 관련 문서에 대한 링크를 제공합니다.
  
|단계|설명|
|:-----|:-----|
|Office 365용 테넌트 계정 만들기   <br/> |Office 365의 [Office 365에 대해 자세히 알아보시고.](https://go.microsoft.com/fwlink/p/?LinkId=254980)  <br/> 사용자 환경이 Office 365에 대해 준비되어 있는지 확인을 위해 시스템 요구 [사항을 참조하세요.](https://products.office.com/office-system-requirements)  <br/> Office 365 설정에 대한 자세한 내용은 [Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982)시작을 참조합니다.  <br/> |
|Office 365 조직에 도메인 추가 및 소유권 확인  <br/> | Office 365 조직에 도메인을 추가한 다음 단계에 따라 Office 365를 사용하여 도메인의 유효성을 검사해야 합니다. 이는 사용자가 도메인의 소유자인지 확인하는 것입니다. <br/> Office 365 조직에 도메인을 추가하려면 Office [365에](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)도메인 추가에 설명된 단계를 따릅니다.  <br/> |
|Active Directory 동기화 설정  <br/> |Active Directory 동기화는 계속해서 Office 365와의 동기화를 유지 관리합니다. 이렇게 하면 각 사용자 계정 및 그룹의 동기화된 버전을 만들 수 있습니다.  <br/> <br> **중요:** 사용자가 Teams 또는 비즈니스용 Skype Online으로 이동되지 않은 경우에도 조직의 모든 비즈니스용 Skype 사용자에 대한 AD 계정을 온라인 배포와 동기화해야 합니다. 모든 사용자를 동기화하지 않는 경우 조직의 온라인 사용자와의 통신이 예상대로 작동하지 않을 수 있습니다. 자세한 내용은 하이브리드 환경에 [대해 Azure AD Connect 구성을 참조하세요.](configure-azure-ad-connect.md)         |
| 비즈니스용 Skype 하이브리드 구성하기 | 세 가지 기본 단계가 있습니다. <br><br> 1. Office 365와 페더러에 연결하도록 프레미스 환경을 구성합니다. <br> 2. Office 365를 신뢰하고 Office 365와 공유 SIP 주소 공간을 사용하도록 프레미스 환경을 구성합니다.<br> 3. Office 365 조직에서 공유 SIP 주소 공간을 사용하도록 설정 <br><br> 또한 Exchange 온-프레미스를 보유하고 있는 경우 Exchange 온-프레미스와 비즈니스용 Skype Online 환경 사이에 OAuth를 구성할 수 있습니다. <br> <br>자세한 내용은 [비즈니스용 Skype 하이브리드 구성을 참조하세요.](configure-federation-with-skype-for-business-online.md)
|파일럿 사용자 이동  <br/> |Teams 또는 비즈니스용 Skype Online에 대한 환경을 준비하고 구성하는 단계를 완료한 후 파일럿 사용자를 온라인 Office 365 조직으로 이동하기 시작할 수 있습니다. 자세한 내용은 사용자를 비즈니스용 [Skype Online으로](move-users-from-on-premises-to-skype-for-business-online.md) 이동하고 사용자를 프레미스에서 [Teams로 이동을 참조하세요.](move-users-from-on-premises-to-Teams.md)  <br/> |
