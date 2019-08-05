---
title: Microsoft 팀의 id 모델 및 인증
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: reference
ms.service: msteams
ms.reviewer: anach
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 클라우드, 동기화 됨, 페더레이션 등의 Microsoft 팀에 있는 다양 한 id 모델에 대해 알아봅니다. Multi-factor authentication에 대해서도 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34e70313d83bfa7873e990a2d77bc165dfd8dfbe
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "36181619"
---
<a name="identity-models-and-authentication-in-microsoft-teams"></a>Microsoft 팀의 id 모델 및 인증
==========================================

Microsoft 팀은 Office 365에서 사용할 수 있는 모든 id 모델을 지원 합니다. 지원 되는 id 모델은 다음과 같습니다.

-   **클라우드 id**:이 모델에서 사용자는 Office 365에서 만들어지고 관리 되며 Azure active directory에 저장 되며, 암호는 Azure active directory에서 확인 됩니다.

-   **동기화 된 id**:이 모델에서 사용자 id는 온-프레미스 서버에서 관리 되며 계정 및 암호 해시가 클라우드와 동기화 됩니다. 사용자는 클라우드에서와 같은 비밀 번호를 온-프레미스와 동일 하 게 입력 하 고 로그인 할 때 Azure Active Directory에서 확인 합니다. 이 모델은 Microsoft Azure Active Directory Connect 도구를 사용 합니다.

-   **페더레이션 id**:이 모델에서는 온-프레미스 id 공급자가 사용자 암호를 사용 하 여 동기화 된 id를 확인 해야 합니다. 이 모델을 사용 하면 암호 해시가 Azure AD에 동기화 될 필요가 없으며 ADFS (Active Directory Federation Services) 또는 타사 id 공급자를 사용 하 여 온-프레미스 Active Directory에 대해 사용자를 인증 합니다.

<a name="configurations"></a>구성
--------------

구현 하 고 사용 하는 데 사용할 id 모델에 따라 구현 요구 사항이 다를 수 있습니다. 배포가 이러한 전제 조건을 충족 하는지 확인 하려면 아래 요구 사항 표를 참조 하세요. 이미 Office 365를 배포한 경우 id 및 인증 방법을 이미 구현한 경우에는이 단계를 건너뛸 수 있습니다.


|Id 모델 |배포 검사 목록  |추가 정보  |
|---------|---------|---------|
|모든     |<ol type="1"><li>Office 365 계획 옵션 비교 및 구독 획득</li><li>Office 365 테 넌 트 만들기</li><li>테 넌 트에 Office 365 라이선스 할당</li><li>도메인 및 관리자 사용자 구성</li><li>Id 모델 관련 지침 계속</li></ol>          |<ul style="list-style-type:none"><li>[Office 365 계획 옵션](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[Office 365 비즈니스 계획 비교](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[비즈니스용 Office 365 구독에 대 한 라이선스 구입](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[구독에 라이선스 추가](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[비즈니스용 Office 365 설정](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[설정 마법사를 사용 하 여 사용자 및 도메인 추가](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li><li>참고: 도움이 필요한 경우 [Microsoft Office 365 팀 용 FastTrack](https://go.microsoft.com/fwlink/?linkid=854618) 을 통해 도움을 받을 수 있습니다.</li></ul>          |
|클라우드 Id     |<ol type="1"><li>Office 365 관리 포털을 사용 하 여 사용자 만들기</li></ol>           |<ul style="list-style-type:none"><li>[Office 365에 개별적으로 또는 대량으로 사용자 추가](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul>         |
|동기화 된 Id     |<ol type="1"><li>Azure AD Connect 설치</li><li>디렉터리 동기화 구성</li><li>온-프레미스 Active Directory 관리 도구를 사용 하 여 사용자 만들기</li></ol>         |<ul style="list-style-type:none"><li>[Office 365에 대 한 디렉터리 동기화 설정](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>참고: 인증을 수행 하려면 Office 365에 대해 암호 해시가 동기화 되어야 합니다.</li></ul>         |
|페더레이션 Id    |<ol type="1"><li>Azure AD Connect 설치</li><li>디렉터리 동기화 구성</li><li>페더레이션 Id 공급자 설치 및 구성 (ADFS 권장)</li><li>온-프레미스 Active Directory 관리 도구를 사용 하 여 사용자 만들기</li></ol>           |<ul style="list-style-type:none"><li>[Office 365에 대 한 디렉터리 동기화 설정](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>[AD FS 배포 계획](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[검사 목록: 페더레이션 서버 팜 배포](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[Adfs에 대 한 엑스트라넷 액세스 구성](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[AD FS와 Azure AD 간의 신뢰 설정](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[ADFS를 사용 하 여 single sign-on 확인 및 관리](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[Azure AD federation compatibility 목록](https://go.microsoft.com/fwlink/?linkid=854625)</li><li>참고: 암호 해시를 Azure Active Directory와 동기화 할 필요는 없습니다.</li></ul>         |

자세한 내용은 [office 365의 로그인 모델 선택](https://go.microsoft.com/fwlink/?linkid=854626) 및 [office 365 Id 및 Azure Active Directory 가이드 이해](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9) 를 참조 하세요.

<a name="multi-factor-authentication"></a>다단계 인증
----------------------------

Office 365 계획은 Office 365 서비스에 대 한 사용자 로그인의 보안을 향상 하는 MFA (다단계 인증)를 지원 합니다. Office 365 용 MFA를 사용 하는 경우 사용자는 암호를 올바르게 입력 한 후에 스마트폰에서 전화 통화, 문자 메시지 또는 앱 알림을 승인 해야 합니다. 이 두 번째 인증 요소가 충족 된 후에만 사용자가 로그인 할 수 있습니다.

다중 요소 인증은 Microsoft 팀을 포함 하는 모든 Office 365 계획에서 지원 됩니다. Microsoft 팀이 포함 된 Office 365 구독 계획에 대 한 자세한 내용은 아래 라이선스 섹션을 참고 하세요.

사용자가 MFA에 등록 되 면 다음에 사용자가 로그인 할 때 두 번째 인증 요소를 설정 하 라는 메시지가 표시 됩니다. 지원 되는 인증 방법은 다음과 같습니다.


|테 넌 트 형식  |사용 가능한 MFA 두 번째 요소 옵션  |상속자  |
|---------|---------|---------|
|**클라우드만**     |Office 365 용 MFA <ul><li>전화 통화</li><li>문자 메시지</li><li>모바일 앱 알림</li><li>모바일 앱 확인 코드</li></ul>        |[Office 365 배포에 대 한 다단계 인증 계획](https://support.office.com/article/Plan-for-multi-factor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba)         |
|**하이브리드 설정 (동기화 또는 페더레이션 Id 모델)**     |<ul><li>Office 365 용 MFA</li><li>Azure MFA 모듈 (ADF 통합)</li><li>실제 또는 가상 스마트 카드 (ADF 통합)</li></ul>         |참고: [AZURE AD federation와 호환 되는 id 공급자](https://go.microsoft.com/fwlink/p/?LinkId=510953) 와 함께 추가 MFA 솔루션을 사용할 수 있습니다.         |
