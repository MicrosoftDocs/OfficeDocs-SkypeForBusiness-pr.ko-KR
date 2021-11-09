---
title: ID 모델 및 인증을 Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 09/25/2020
ms.topic: reference
ms.service: msteams
ms.reviewer: anwara
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: 클라우드 전용 및 하이브리드와 같은 Microsoft Teams ID 모델에 대해 자세히 알아보습니다. 또한 다단계 인증에 대해 자세히 알아보습니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c12e7242241c8c6d7ac03bc3c66804198acd746e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836066"
---
# <a name="identity-models-and-authentication-for-microsoft-teams"></a>ID 모델 및 인증을 Microsoft Teams

Microsoft Teams 포함되는 Microsoft 365 및 Office 365 모든 ID 모델을 지원합니다.

- **클라우드 전용**: 사용자 계정은 Azure AD(Microsoft 365 또는 Office 365 및 Azure Active Directory 관리됩니다. 사용자 로그인 자격 증명(계정 이름 및 암호)은 Azure AD에서 유효성을 검사합니다.

- **하이브리드**: 사용자 계정은 일반적으로 AD DS(Active Directory Domain Services) 포리스트에서 관리됩니다. 구성에 따라 자격 증명 유효성 검사는 Azure AD, AD DS 또는 페더링된 ID 공급자에서 수행될 수 있습니다. 이 모델은 Azure AD를 사용하여 AD DS에서 Azure AD로 디렉터리 동기화를 커넥트.

자세한 내용은 ID [Microsoft 365 및 Azure AD 를 참조하세요.](/microsoft-365/enterprise/about-microsoft-365-identity)

## <a name="configurations"></a>구성

사용하는 ID 모델 및 구성에 대한 조직의 결정에 따라 구현 단계가 다를 수 있습니다.

사용자 및 ID 모델을 Microsoft 365 Office 365 아직 배포하지 않은 경우 이 표를 사용 합니다. 

|ID 모델 |배포 검사 목록  |추가 정보  |
|---------|---------|---------|
|모두     |<ol type="1"><li>Microsoft 365 및 Office 365 옵션을 비교하고 구독 및 테넌트를 얻습니다.</li><li>테넌트에 Microsoft 365 또는 Office 365 조직을 만들 수 있습니다.</li><li>테넌트에 Microsoft 365 Office 365 라이선스 구입</li><li>도메인 및 관리자 사용자 계정을 구성합니다.</li></ol>  |<ul><li>[Office 365 옵션](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)</li><li>[비즈니스 Microsoft 365 비교](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[구독 라이선스 구입 또는 제거](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[구독에 라이선스 추가](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[비즈니스용 Microsoft 365 설정](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[설정 마법사를 통해 도메인 추가](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li></ul><br>[Microsoft FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) 지원할 수 있습니다.  |
|클라우드 ID     |<ul><li>사용자 계정을 Microsoft 365 관리 센터</li></ul> |<ul><li>[사용자 추가 및 라이선스 할당](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul> |
|하이브리드 ID     |<ol type="1"><li>Azure AD 커넥트.</li><li>디렉터리 동기화를 구성합니다.</li><li>AD DS 도구를 사용하여 사용자 및 그룹을 관리합니다.</li></ol> |<ul><li>[디렉터리 동기화 설정](/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
|페더리드 인증이 있는 하이브리드 ID    |<ol type="1"><li>AD FS와 같은 페더리드 ID 공급자를 설치하고 구성합니다.</li><li>Azure AD 커넥트 디렉터리 동기화 및 페더리드 인증을 구성합니다.</li><li>AD DS 도구를 사용하여 사용자 및 그룹을 관리합니다.</li></ol> |<ul><li>[AD FS 배포 계획](/previous-versions/azure/azure-services/dn151324(v=azure.100))</li><li>[검사 목록: 페더전 서버 팜 배포](/previous-versions/azure/azure-services/dn528856(v=azure.100))</li><li>[AD FS에 대한 엑스트라넷 액세스 구성](/previous-versions/azure/azure-services/dn528859(v=azure.100))</li><li>[AD FS와 Azure AD 간에 트러스트 설정](/previous-versions/azure/azure-services/jj205461(v=azure.100))</li><li>[ADFS를 사용하여 Single Sign-On 확인 및 관리](/previous-versions/azure/azure-services/jj151809(v=azure.100))</li><li>[디렉터리 동기화 설정](/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
||||

## <a name="multi-factor-authentication"></a>다단계 인증

암호는 컴퓨터 또는 온라인 서비스에 로그인하기 위한 가장 일반적인 인증 방법이지만 가장 취약합니다. 사람들은 쉬운 암호를 선택하고 여러 컴퓨터 및 서비스에 대한 여러 로그인에 동일한 암호를 사용할 수 있습니다. 

로그인에 대한 추가 보안 수준을 제공하려면 암호와 같은 추가 확인 방법이 필요한 MFA(다단계 인증)를 사용합니다.

- 사용자가 확인 코드를 입력해야 하는 휴대폰으로 전송된 문자 메시지입니다.
- 전화 통화.
- Microsoft Authenticator 앱입니다.
- 하이브리드 ID 및 페더리드 인증에서 사용할 수 있는 다른 메서드입니다.

MFA는 Microsoft 365 또는 Office 365 포함된 모든 Microsoft Teams. 최소한 서비스 관리자와 같은 관리자 역할이 할당된 [](/microsoft-365/admin/add-users/about-admin-roles)해당 계정에 대해 MFA가 Teams 것이 좋습니다.

또한 사용자에게 MFA를 롤아웃해야 합니다. 사용자가 MFA에 등록된 후 다음에 로그인할 때 추가 확인 방법을 설정해달라는 메시지가 표시됩니다. 

자세한 내용은 에 대한 [다단계 인증을 Microsoft 365.](/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)