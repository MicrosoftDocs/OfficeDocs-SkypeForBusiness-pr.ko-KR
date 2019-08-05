---
title: 하이브리드 연결 구성 | 비즈니스용 Skype 서버 2019 연결 배포
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 비즈니스용 Skype 서버와 비즈니스용 Skype Online 간의 하이브리드 연결을 구현 하는 방법에 대해 설명 합니다.
ms.openlocfilehash: ab7fb32c16e57e554c702a7b0f29ba350c1eedbe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185460"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>비즈니스용 Skype 서버와 Office 365 하이브리드 연결 구성

**요약:** 비즈니스용 Skype 서버와 팀 또는 비즈니스용 Skype Online 간에 하이브리드 연결을 구성 하는 방법을 알아보려면이 항목을 참조 하세요.  하이브리드 연결을 사용 하면 온-프레미스 사용자를 팀 또는 비즈니스용 Skype Online으로 이동 하 고 사용자가 클라우드 서비스를 활용할 수 있습니다.
  
이 항목의 단계를 수행 하기 전에 [비즈니스용 Skype 서버와 Office 365 간에 하이브리드 연결](plan-hybrid-connectivity.md)을 읽을 수 있어야 합니다.
  
다음 표에서는 비즈니스용 Skype 하이브리드 연결을 구성 하는 데 필요한 작업을 보여 주고 자세한 내용은 관련 문서에 대 한 링크를 제공 합니다.
  
|단계만|설명|
|:-----|:-----|
|Office 365에 대 한 테 넌 트 계정 만들기   <br/> |Office [365](https://go.microsoft.com/fwlink/p/?LinkId=254980)의 office 365에 대해 알아보세요.  <br/> Office 365에 대 한 환경이 준비 되었는지 확인 하려면 [시스템 요구 사항을](https://products.office.com/en-US/office-system-requirements)참조 하세요.  <br/> Office 365 설정에 대 한 자세한 내용은 [office 365 시작](https://go.microsoft.com/fwlink/p/?LinkId=254982)을 참조 하세요.  <br/> |
|Office 365 테 넌 트에 도메인 추가 및 소유권 확인  <br/> | Office 365 테 넌 트에 도메인을 추가한 다음 단계를 따라 Office 365 도메인의 유효성을 검사 해야 합니다. 이는 사용자가 도메인의 소유자 인지 확인 하는 것입니다. <br/> Office 365 테 넌 트에 도메인을 추가 하려면 [office 365에 도메인 추가](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)에 설명 된 단계를 따릅니다.  <br/> |
|Active Directory 동기화 설정  <br/> |Active Directory 동기화는 온-프레미스 Active Directory를 계속 해 서 Office 365와 동기화 상태로 유지 합니다. 이렇게 하면 각 사용자 계정 및 그룹의 동기화 된 버전을 만들 수 있습니다.  <br/> <br> **중요:** 사용자가 비즈니스용 Skype Online으로 이동 하지 않은 경우에도 조직의 모든 비즈니스용 Skype 사용자에 대 한 광고 계정을 온-프레미스 및 온라인 배포로 동기화 해야 합니다. 모든 사용자를 동기화 하지 않으면 조직에서 온-프레미스 및 온라인 사용자 간의 통신이 예상 대로 작동 하지 않을 수 있습니다. 자세한 내용은 [하이브리드 환경에 대 한 AZURE AD Connect 구성을](configure-azure-ad-connect.md)참조 하세요.         |
| 비즈니스용 Skype 하이브리드 구성 | 다음과 같은 세 가지 기본 단계가 있습니다. <br><br> 1. Office 365와 페더레이션 할 온-프레미스 환경을 구성 합니다. <br> 2. Office 365을 신뢰 하도록 온-프레미스 환경을 구성 하 고 Office 365에서 공유 SIP 주소 공간을 사용 하도록 설정 합니다.<br> 3. Office 365 테 넌 트에서 공유 SIP 주소 공간을 사용 하도록 설정 합니다. <br><br> 또한 Exchange 온-프레미스를 사용 하는 경우 Exchange 온-프레미스 및 비즈니스용 Skype Online 환경 간에 OAuth를 구성할 수 있습니다. <br> <br>자세한 내용은 [비즈니스용 Skype 하이브리드 구성을](configure-federation-with-skype-for-business-online.md)참조 하세요.
|파일럿 사용자 이동  <br/> |팀 또는 비즈니스용 Skype Online에 대 한 환경을 준비 하 고 구성 하는 단계를 완료 한 후에는 파일럿 사용자를 온라인 Office 365 테 넌 트로 이동할 수 있습니다. 자세한 내용은 온 [-프레미스에서 비즈니스용 Skype Online으로 이동](move-users-from-on-premises-to-skype-for-business-online.md) 및 [사용자를 온-프레미스에서 팀으로 이동](move-users-from-on-premises-to-Teams.md)을 참조 하세요.  <br/> |