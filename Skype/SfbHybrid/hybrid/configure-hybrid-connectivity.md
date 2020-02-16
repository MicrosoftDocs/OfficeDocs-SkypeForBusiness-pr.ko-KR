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
description: 비즈니스용 Skype 서버 및 비즈니스용 Skype Online 간의 하이브리드 연결을 구현 하기 위한 지침입니다.
ms.openlocfilehash: 54029297cb17da79d706f62ecdf9109747f9ce20
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008620"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>비즈니스용 Skype 서버 및 Office 365 간 하이브리드 연결 구성

**요약:** 비즈니스용 Skype 서버 및 팀과 비즈니스용 Skype Online 간의 하이브리드 연결을 구성 하는 방법을 알아보려면이 항목을 읽어 보십시오.  하이브리드 연결을 사용 하 여 온-프레미스 사용자를 팀 또는 비즈니스용 Skype 온라인으로 이동 하 고 사용자가 클라우드 서비스를 활용할 수 있습니다.
  
이 항목의 단계를 수행 하기 전에 [비즈니스용 Skype 서버 및 Office 365 간에 하이브리드 연결 계획](plan-hybrid-connectivity.md)을 읽어야 합니다.
  
다음 표에서는 비즈니스용 Skype 하이브리드 연결을 구성 하는 데 필요한 작업을 보여 주고 자세한 내용은 관련 문서에 대 한 링크를 제공 합니다.
  
|단계|설명|
|:-----|:-----|
|Office 365에 대 한 테 넌 트 계정 만들기   <br/> |[Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980)의 office 365에 대해 알아봅니다.  <br/> 사용자 환경이 Office 365에 대 한 준비가 되었는지 확인 하려면 [시스템 요구 사항을](https://products.office.com/office-system-requirements)참조 하세요.  <br/> Office 365을 설정 하는 방법에 대 한 자세한 내용은 [office 365 시작](https://go.microsoft.com/fwlink/p/?LinkId=254982)을 참조 하십시오.  <br/> |
|Office 365 테 넌 트에 도메인 추가 및 소유권 확인  <br/> | Office 365 테 넌 트에 도메인을 추가 하 고 해당 단계에 따라 Office 365 도메인의 유효성을 검사 해야 합니다. 이는 사용자가 도메인의 소유자 인지 확인 하기 위한 것입니다. <br/> Office 365 테 넌 트에 도메인을 추가 하려면 [office 365에 도메인 추가](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)에 설명 된 단계를 수행 합니다.  <br/> |
|Active Directory 동기화 설정  <br/> |Active Directory 동기화를 사용 하면 온-프레미스 Active Directory가 계속 해 서 Office 365와 동기화 됩니다. 이렇게 하면 각 사용자 계정 및 그룹의 동기화 된 버전을 만들 수 있습니다.  <br/> <br> **중요:** 사용자가 팀 또는 비즈니스용 Skype Online으로 이동 하지 않은 경우에도 조직의 모든 비즈니스용 Skype 사용자에 대해 AD 계정을 온-프레미스 및 온라인 배포 사이에 동기화 해야 합니다. 모든 사용자를 동기화 하지 않으면 조직에서 온-프레미스 및 온라인 사용자 간의 통신이 예상 대로 작동 하지 않을 수 있습니다. 자세한 내용은 [하이브리드 환경에 대 한 AZURE AD Connect 구성을](configure-azure-ad-connect.md)참조 하세요.         |
| 비즈니스용 Skype 하이브리드 구성하기 | 세 가지 기본 단계가 있습니다. <br><br> 1. Office 365와 페더레이션 할 온-프레미스 환경을 구성 합니다. <br> 2. Office 365을 신뢰 하도록 온-프레미스 환경을 구성 하 고 Office 365와 공유 SIP 주소 공간을 사용 하도록 설정 합니다.<br> 3. Office 365 테 넌 트에서 공유 SIP 주소 공간을 사용 하도록 설정 합니다. <br><br> 또한 Exchange 온-프레미스를 보유하고 있는 경우 Exchange 온-프레미스와 비즈니스용 Skype Online 환경 사이에 OAuth를 구성할 수 있습니다. <br> <br>자세한 내용은 [비즈니스용 Skype 하이브리드 구성을](configure-federation-with-skype-for-business-online.md)참조 하세요.
|파일럿 사용자 이동  <br/> |팀 또는 비즈니스용 Skype Online에 대해 환경을 준비 하 고 구성 하는 단계를 완료 한 후 파일럿 사용자를 온라인 Office 365 테 넌 트로 이동 하는 작업을 시작할 수 있습니다. 자세한 내용은 온 [-프레미스에서 비즈니스용 Skype Online으로 사용자 이동을](move-users-from-on-premises-to-skype-for-business-online.md) 참조 하 고 [사용자를 온-프레미스에서 팀으로 이동](move-users-from-on-premises-to-Teams.md)합니다.  <br/> |