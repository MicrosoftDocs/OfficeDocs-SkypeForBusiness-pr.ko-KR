---
title: Microsoft 팀을 위한 Office 365 서비스 사용을 위한 온 보 딩 검사 목록
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 팀에 대해 Office 365을 구성할 때이 검사 목록의 핵심, 할 일 작업 및 활동을 따릅니다.
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 646a820888c47b0e5ecd8cd491fb9949160cb42c
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2020
ms.locfileid: "41862878"
---
# <a name="enable-office-365"></a>Office 365 사용
 
| 아니요 | 활동 또는 작업| 설명| 완료? | 추가 정보|
|----|-----------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Office 365 테 넌 트 만들기| 조직에서 팀의 혜택을 누릴 수 있으려면 먼저 Office 365 테 넌 트를 설정 해야 합니다. Office 365 테 넌 트가 있는지 확인 하려면 **추가 정보** 열의 지침을 참조 하세요. | | [비즈니스용 Office 365 설정](https://support.office.com/article/Set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa) <br/><br/>[추가 지원이 필요한 경우 Office 365 team에 대 한 Microsoft FastTrack을 통해 도움을 받을 수 있습니다.](https://fasttrack.microsoft.com/office) |
| 2  | Office 365 라이선스 구입 | 팀 구상 단계에서 수행한 작업의 결과에 따라 조달 그룹과 협력 하 여 조직에서 필요한 라이선스 Sku 또는 추가 기능 서비스를 구입 했으며 테 넌 트에 할당할 준비가 되었는지 확인 합니다. | | [Microsoft 팀 용 Office 365 라이선스](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing) <br/><br/>[비즈니스용 Office 365 구독에 대 한 라이선스 구입](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1) |
| 3  | 테 넌 트에 Office 365 라이선스 할당 | 일반적으로 사용자 또는 라이선스 관리자는 Microsoft 라이선스의 링크를 수신 하 여 Office 365 테 넌 트에 라이선스를 추가 합니다. <br/><br/>라이선스를 구입 하는 데 사용한 채널에 따라 **추가 정보** 열에 나열 된 가이드 중 하나를 방문 해야 할 수 있습니다. | | [제품 키를 사용 하 여 지불한 구독에 라이선스 추가](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53) <br/><br/>[볼륨 라이선스 서비스 센터를 통해 구입한 구독에 라이선스 추가](https://support.office.com/article/Add-licenses-to-a-subscription-purchased-through-the-Volume-Licensing-Service-Center-82ba88fa-ebdf-4d44-a7b3-cea82b25d71a) |
| 4(tcp/ipv4)  | 선택 사항: 통신 크레딧을 사용 하도록 설정 | 통신 크레딧은 조직의 회의 브리지 전화 번호에 대 한 무료 액세스를 제공 하거나, 회의 이끌이에 게 국제 모임 참가자에 게 전화를 걸 수 있는 기능을 제공 하는 데 사용 하는 선택적 기능입니다. <br/><br/>볼륨 및 라이선스 조직은 표준 오디오 회의 사용자별 라이선스 외에도 분당 유료 서비스를 선택 하 여 오디오 회의 기능을 사용할 수 있습니다. <br/><br/>조직의 통신 크레딧이 필요한 지 여부를 결정 하 고 (해당 하는 경우) 통신 크레딧 추가 기능 라이선스를 테 넌 트에 추가 하 여 사용 하도록 설정 합니다. | | [통신 크레딧이란?](what-are-communications-credits.md) <br/><br/>[조직에 사용할 통신 크레딧 설정](set-up-communications-credits-for-your-organization.md) <br/><br/>[오디오 회의 분당 요금](audio-conferencing-pay-per-minute.md) |
| 5mb  | Office 365 테 넌 트에 대해 라이선스를 사용할 수 있는지 확인 | Office 365 관리 포털로 이동 하 여 Office 365 테 넌 트에 예상 되는 라이선스 Sku 및 수량이 표시 되는지 확인 합니다. <br/><br/>이 프로세스를 통해 **추가 정보** 에 대 한 참조를 사용 합니다. | | [비즈니스용 Office 365 구독에는 무엇이 있나요?](https://support.office.com/article/What-Office-365-for-business-subscription-do-I-have-092252f8-08df-4cdb-a8d2-b8653caa29a1) |
| 26  | Id에 대 한 환경을 구성 합니다. | 사용자는 Office 365에서 직접 (온라인 배포 모델에서) 만들거나 온-프레미스 Active Directory에서 Office 365 테 넌 트로 동기화 할 수 있습니다. <br/><br/>클라우드 id, 동기화 된 id 또는 페더레이션 id를 사용 해야 하는지 여부를 결정 합니다. 적절 한 id 형식을 결정 하는 것은이 검사 목록의 범위를 벗어났습니다. 그러나 **추가 정보** 열에서 이러한 옵션에 대 한 정보 링크를 찾을 수 있습니다. <br/><br/>**참고:** 동기화 또는 페더레이션 id를 사용 하는 경우에는 온-프레미스 Upn (사용자 계정 이름)이 Office 365 Upn과 일치 하며 모든 필수 특성이 Azure AD Connect와 동기화 되도록 구성 되어 있는지 확인 합니다. 팀에 필요한 특성을 보려면 비즈니스용 Skype Online에 대 한 특성 목록을 사용 하세요. | | [Office 365 id 및 Azure Active Directory 이해](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9) <br/><br/>[Office 365에 대 한 디렉터리 동기화를 통해 사용자 프로 비전 준비](https://support.office.com/article/Prepare-to-provision-users-through-directory-synchronization-to-Office-365-01920974-9e6f-4331-a370-13aea4e82b3e) <br/><br/>[Azure AD Connect 동기화: 특성이 Azure Active Directory와 동기화 됨](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-attributes-synchronized) |
| 7  | 테 넌 트 관리자 확인 | 보안 팀과 협력 하 여 Office 365 관리 모델을 개발 합니다. <br/><br/>모든 테 넌 트 및 서비스 관리자를 식별 하 고 문서화 하세요. | | [Office 365 관리자 역할 정보](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) |
| 20cm(8  | 테 넌 트에 대 한 관리 역할 구현 | 관리 모델이 조직의 요구 사항에 맞는지 확인 하 고 관리자에 게 Office 365 관리자 역할을 할당 합니다. | | [Office 365 비즈니스 에디션에서 관리자 역할 할당](https://support.office.com/article/Assign-admin-roles-in-Office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) |
| 되었는지  | CQD (통화 품질 대시보드)에 로그인 하 여 건물 정보를 업로드 합니다. | 모든 팀 구축은 팀을 사용 하는 모든 통화의 품질 및 안정성에 대 한 통찰력을 얻으려면 CQD를 활용 해야 합니다. <br><br>**추가 정보** 열에 나열 된 CQD 지침을 사용 하 여이 도구를 최대한 활용 하세요. | | [서비스 관리 및 품질 계획](https://docs.microsoft.com/MicrosoftTeams/prepare-network) <br/><br/>[품질 환경 검토 가이드](https://aka.ms/qerguide) <br/><br/>[품질 경험 검토 서식 파일](https://aka.ms/qertemplates) <br/><br/>[Microsoft 팀 및 비즈니스용 Skype Online에 대 한 통화 품질 대시보드 켜기 및 사용](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-for-Microsoft-Teams-and-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)<br><br>[건물 정보 업로드](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard?#upload-building-information) |
| 1천만  | 건물 정보가 처리 되었는지 확인 하 고 테 넌 트에 대해 CQD (통화 품질 대시보드)가 작동 하도록 합니다. | | | [통화 품질 대시보드](https://cqd.lync.com) |
