---
title: Microsoft 팀의 id 모델 및 인증
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 09/25/2020
ms.topic: reference
ms.service: msteams
ms.reviewer: anwara
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: 클라우드 전용 및 하이브리드 등의 Microsoft 팀에 대 한 다양 한 id 모델에 대해 알아봅니다. Multi-factor authentication에 대해서도 알아봅니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 40a06ce75c3ae7a4f85eb1c93064ba3d80c13fc0
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277118"
---
# <a name="identity-models-and-authentication-for-microsoft-teams"></a>Microsoft 팀의 id 모델 및 인증

Microsoft 팀은 다음을 포함 하 여 Microsoft 365 및 Office 365에서 사용할 수 있는 모든 id 모델을 지원 합니다.

- **클라우드 전용**: 사용자 계정은 Microsoft 365 또는 Office 365에서 만들어지고 관리 되며 Azure Active Directory (azure AD)에 저장 됩니다. Azure AD에서 사용자 로그인 자격 증명 (계정 이름 및 암호)의 유효성을 검사 합니다.

- **하이브리드**: 사용자 계정은 일반적으로 온-프레미스 AD DS (Active Directory 도메인 서비스) 포리스트에서 관리 합니다. 구성에 따라 Azure AD, AD DS 또는 페더레이션 id 공급자에서 자격 증명 유효성 검사를 수행할 수 있습니다. 이 모델은 Azure AD Connect와 함께 AD DS에서 Azure AD로의 디렉터리 동기화를 사용 합니다.

자세한 내용은 [Microsoft 365 id 모델 및 AZURE AD](https://docs.microsoft.com/microsoft-365/enterprise/about-microsoft-365-identity)를 참조 하세요.

## <a name="configurations"></a>구성

사용 하는 id 모델 및 구성에 대 한 조직의 결정에 따라 구현 단계가 다를 수 있습니다.

Microsoft 365 또는 Office 365 및 id 모델을 아직 배포 하지 않은 경우 다음 표를 사용 하세요. 

|Id 모델 |배포 검사 목록  |추가 정보  |
|---------|---------|---------|
|모든     |<ol type="1"><li>Microsoft 365 및 Office 365 계획 옵션을 비교 하 고 구독과 테 넌 트를 받습니다.</li><li>테 넌 트에 대 한 Microsoft 365 또는 Office 365 조 직을 만듭니다.</li><li>테 넌 트에 대 한 Microsoft 365 또는 Office 365 라이선스 구입</li><li>도메인 및 관리자 사용자 계정을 구성 합니다.</li></ol>  |<ul><li>[Office 365 계획 옵션](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[비즈니스 요금제에 대 한 Microsoft 365 비교](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[구독 라이선스 구입 또는 제거](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[구독에 라이선스 추가](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[비즈니스용 Microsoft 365 설정](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[설정 마법사를 사용 하 여 도메인 추가](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li></ul><br>[Microsoft FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) 을 통해 도움을 받을 수 있습니다.  |
|클라우드 id     |<ul><li>Microsoft 365 관리 센터를 사용 하 여 사용자 계정 만들기</li></ul> |<ul style="list-style-type:none"><li>[사용자 추가 및 라이선스 할당](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul> |
|하이브리드 id     |<ol type="1"><li>Azure AD Connect를 설치 합니다.</li><li>디렉터리 동기화를 구성 합니다.</li><li>AD DS 도구를 사용 하 여 사용자 및 그룹을 관리 합니다.</li></ol> |<ul style="list-style-type:none"><li>[디렉터리 동기화 설정](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
|페더레이션 인증을 사용 하는 하이브리드 id    |<ol type="1"><li>AD FS와 같은 페더레이션 id 공급자를 설치 하 고 구성 합니다.</li><li>Azure AD Connect를 설치 하 고 디렉터리 동기화 및 페더레이션 인증을 구성 합니다.</li><li>AD DS 도구를 사용 하 여 사용자 및 그룹을 관리 합니다.</li></ol> |<ul><li>[AD FS 배포 계획](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[검사 목록: 페더레이션 서버 팜 배포](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[Adfs에 대 한 엑스트라넷 액세스 구성](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[AD FS와 Azure AD 간의 신뢰 설정](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[ADFS를 사용 하 여 single sign-on 확인 및 관리](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[디렉터리 동기화 설정](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
||||

## <a name="multi-factor-authentication"></a>다단계 인증

암호는 컴퓨터 또는 온라인 서비스에 로그인 할 때 가장 일반적으로 사용할 수 있는 인증 방법 이지만 가장 취약 합니다. 사용자는 쉽게 암호를 선택 하 고 여러 로그인에 동일한 암호를 다양 한 컴퓨터 및 서비스에 사용할 수 있습니다. 

로그인에 대 한 추가 수준의 보안을 제공 하기 위해 다음과 같은 암호와 추가 확인 방법을 모두 필요로 하는 MFA (다단계 인증)를 사용 합니다.

- 사용자가 확인 코드를 입력 해야 하는 전화기로 전송 된 문자 메시지입니다.
- 전화 통화.
- Microsoft Authenticator 스마트 폰 앱.
- 하이브리드 id 및 페더레이션 인증에서 사용할 수 있는 다른 방법

MFA는 Microsoft 팀이 포함 된 Microsoft 365 또는 Office 365 요금제에서 지원 됩니다. 팀 서비스 관리자와 같이 [관리자 역할이 할당](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)된 해당 계정에 대 한 MFA가 최소한으로 필요한 지 여부를 적극 권장 합니다.

또한 사용자에 게 MFA를 배포 해야 합니다. 사용자가 MFA에 등록 되 면 다음에 로그인 할 때 추가 확인 방법을 설정 하 라는 메시지가 표시 됩니다. 

자세한 내용은 [Microsoft 365에 대 한 다단계 인증](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)을 참조 하세요.
