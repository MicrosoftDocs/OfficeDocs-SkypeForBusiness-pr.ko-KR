---
title: 온보드 검사 목록 - Microsoft 365 또는 Office 365 서비스 사용
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Microsoft 365 또는 Teams용 Office 365를 구성할 때 이 검사 목록의 핵심 할 일 작업 및 활동을 수행합니다.
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9f9d9e40968d8d94f92b3fee5807d0d16bd2c0e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802298"
---
# <a name="enable-microsoft-365-or-office-365"></a>Microsoft 365 또는 Office 365 사용
 
| 아니요 | 작업 또는 작업| 설명| 완료된 경우 | 추가 정보|
|----|-----------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Microsoft 365 또는 Office 365 조직 만들기| 조직에서 Teams의 혜택을 사용하려면 먼저 Microsoft 365 또는 Office 365 조직을 설정해야 합니다. Microsoft 365 또는 Office 365 조직이 없는 경우 추가 정보 열의 지침을 **참조하세요.** | | [비즈니스용 Microsoft 365 또는 Office 365 설정](https://support.office.com/article/Set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa) <br/><br/>[추가 지원이 필요한 경우 Microsoft 365 또는 Office 365용 Microsoft FastTrack 팀을 지원할 수 있습니다.](https://fasttrack.microsoft.com/office) |
| 2  | Microsoft 365 또는 Office 365 라이선스 구입 | Teams Envision 단계에서 작업한 결과에 따라 조달 그룹과 협의하여 조직이 필요한 라이선스 SCUR 또는 추가 기능 서비스를 구입하고 테넌트에 할당할 준비가 되도록 합니다. | | [Microsoft Teams 서비스 설명](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description) <br/><br/>[Microsoft 365 또는 비즈니스용 Office 365 구독에 대한 라이선스 구입](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1) |
| 3  | 이끌이에게 Microsoft 365 또는 Office 365 라이선스 할당 | 일반적으로 사용자 또는 라이선스 관리자는 Microsoft 라이선스에서 Microsoft 365 또는 Office 365 조직에 라이선스를 추가하는 링크를 받게 됩니다. <br/><br/>라이선스를 구매하는 데 사용한 채널에 따라 추가 정보 열에 나열된 가이드 중 하나를 **방문해야 할 수** 있습니다. | | [제품 키를 사용하여 유료 구독에 라이선스 추가](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53) <br/><br/>[볼륨 라이선스 서비스 센터를 통해 구입한 구독에 라이선스 추가](https://support.office.com/article/Add-licenses-to-a-subscription-purchased-through-the-Volume-Licensing-Service-Center-82ba88fa-ebdf-4d44-a7b3-cea82b25d71a) |
| 4  | 선택 사항: 통신 크레딧 사용 | 통신 크레딧은 조직의 전화 회의 브리지 전화 번호에 대한 무료 액세스를 제공하거나 회의 이끌이에게 국제 모임 참가자에게 전화를 걸 수 있는 기능을 제공하는 데 사용하는 선택적 기능입니다. <br/><br/>볼륨 및 라이선스 조직은 표준 사용자당 오디오 회의 라이선스 외에도 분당 유료 제안을 선택하면 오디오 회의 기능을 사용할 수 있습니다. <br/><br/>조직에 통신 크레딧이 필요한지 여부를 결정하고, 필요한 경우 테넌트에 통신 크레딧 추가 기능 라이선스를 추가하여 사용하도록 설정합니다. | | [통신 크레딧이란?](what-are-communications-credits.md) <br/><br/>[조직에 사용할 통신 크레딧 설정](set-up-communications-credits-for-your-organization.md) <br/><br/>[오디오 회의 분당 요금](audio-conferencing-pay-per-minute.md) |
| 5  | Microsoft 365 또는 Office 365 조직에서 라이선스를 사용할 수 있도록 하는지 확인 | Microsoft 365 관리 센터로 이동하여 Microsoft 365 또는 Office 365 조직에서 예상하는 라이선스 SKUS 및 수량을 표시하는지 확인해야 합니다. <br/><br/>추가 **정보의** 참조를 사용하여 이 프로세스를 안내합니다. | | [어떤 Microsoft 365 또는 비즈니스용 Office 365 구독이 있나요?](https://support.office.com/article/What-Office-365-for-business-subscription-do-I-have-092252f8-08df-4cdb-a8d2-b8653caa29a1) |
| 6  | ID에 대한 환경을 구성합니다. | 사용자를 Microsoft 365 또는 Office 365에서 직접 만들거나(온라인 배포 모델에서) Microsoft 365 또는 Office 365 조직으로 동기화할 수 있습니다. <br/><br/>클라우드 ID, 동기화된 ID 또는 페더러드 ID를 사용할지 여부를 판단합니다. 적절한 ID 유형을 결정하는 것은 이 검사 목록의 범위를 벗어날 수 있습니다. 그러나 추가 정보 열에서 이러한 옵션에 대한 정보에 대한 **링크를 찾을 수** 있습니다. <br/><br/>**참고:** 동기화된 ID 또는 페더링된 ID를 사용하는 경우, Microsoft 365 또는 Office 365 UPNS와 프레미스 UPNS(사용자 계정 이름)가 일치하는지, 모든 필수 특성이 Azure AD Connect와 동기화되도록 구성되어 있는지를 확인하세요. Teams에 필요한 특성의 경우 비즈니스용 Skype Online의 특성 목록을 사용하세요. | | [Microsoft 365 또는 Office 365 ID 및 Azure Active Directory 이해](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9) <br/><br/>[Microsoft 365 또는 Office 365에 디렉터리 동기화를 통해 사용자 프로비전 준비](https://support.office.com/article/Prepare-to-provision-users-through-directory-synchronization-to-Office-365-01920974-9e6f-4331-a370-13aea4e82b3e) <br/><br/>[Azure AD Connect 동기화: Azure Active Directory에 동기화된 특성](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-attributes-synchronized) |
| 7  | 테넌트 관리자 확인 | 보안 팀과 함께 Microsoft 365 또는 Office 365 관리 모델을 개발합니다. <br/><br/>모든 테넌트 및 서비스 관리자를 식별하고 문서화해야 합니다. | | [Microsoft 365 또는 Office 365 관리자 역할](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) |
| 8  | 테넌트에 대한 관리 역할 구현 | 관리 모델이 조직의 요구 사항을 충족하는지 확인하고 관리자에게 Microsoft 365 또는 Office 365 관리자 역할을 할당합니다. | | [Microsoft 365 또는 비즈니스용 Office 365에서 관리자 역할 할당](https://support.office.com/article/Assign-admin-roles-in-Office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) |
| 9  | CQD(통화 품질 대시보드)에 로그인하여 건물 정보를 업로드합니다. | 모든 Teams 배포는 CQD를 활용하여 Teams를 사용하는 모든 호출의 품질과 안정성에 대한 인사이트를 얻을 수 있습니다. <br><br>추가 정보 열에 나열된  CQD 지침을 사용하여 이 도구를 활용하세요. | | [서비스 관리 및 품질 계획](https://docs.microsoft.com/MicrosoftTeams/prepare-network) <br/><br/>[품질 환경 검토 가이드](https://aka.ms/qerguide) <br/><br/>[품질 환경 검토 서식 파일](https://aka.ms/qertemplates) <br/><br/>[Microsoft Teams 및 비즈니스용 Skype Online에 대한 통화 품질 대시보드 켜기 및 사용](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-for-Microsoft-Teams-and-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)<br><br>[건물 정보 업로드](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard?#upload-building-information) |
| 10  | 건물 정보가 처리된 후 CQD(통화 품질 대시보드)가 테넌트에 대해 작동할 수 있는지 유효성을 검사합니다. | | | [통화 품질 대시보드](https://cqd.teams.microsoft.com) |
