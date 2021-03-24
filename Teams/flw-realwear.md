---
title: RealWear 클라이언트용 Microsoft Teams에 대한 IT 관리자 정보(미리보기)
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: A, ITAdmin은 RealWear 클라이언트용 Microsoft Teams에 대해 안내합니다.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 222cb12e38061c81a860092f90bf42d5412fdb63
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092286"
---
# <a name="microsoft-teams-for-realwear"></a>RealWear용 Microsoft Teams

이 문서는 RealWear head wearables용 Microsoft Teams 클라이언트에 대해 설명합니다. RealWear HMT-1 및 HMT-1Z1을 사용하는 최전방 작업자는 이제 팀에서 화상 통화를 사용하여 원격 전문가와 협력할 수 있습니다. RealWear용 Teams는 음성으로 제어되는 사용자 인터페이스를 통해 현장 작업자가 100 % 핸즈프리 상태를 유지하면서 크고 위험한 환경에서 상황 인식을 유지합니다. 필드 직원은 실시간으로 해당 사용자에게 표시되는 내용을 표시하여 문제를 해결하는 시간을 단축하고 비싼 가동 중지 시간의 위험을 줄일 수 있습니다.

## <a name="how-to-deploy-microsoft-teams-for-realwear"></a>RealWear용 Microsoft Teams를 배포하는 방법

- RealWear 장치를 릴리스 11.2이상으로 업데이트했습니다. [여기](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/)에서 자세한 내용을 확인하세요.
- Realwear용 Microsoft Teams 클라이언트를 배포하는 데 필요한 [RealWear Foresight](https://cloud.realwear.com/)에 액세스합니다.

## <a name="required-licenses"></a>필수 라이선스

Microsoft Teams 라이선스는 Microsoft 365 및 Office 365 구독의 일부입니다. RealWear용 Teams를 사용하는 데 별도의 라이선스가 필요하지 않습니다. 팀을 얻는 방법에 대한 자세한 내용은  [Microsoft Teams에 액세스하는 방법](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)을 참조하세요.

## <a name="managing-realwear-devices"></a>RealWear 장치 관리

### <a name="microsoft-endpoint-manager"></a>Microsoft 엔드포인트 관리자

RealWear 장치는 Android 장치 관리자 모드를 사용하여 관리할 수 있습니다. 장치에 현재 Google 모바일 서비스(GMS)가 제공되지 않으므로 Android Enterprise를 통한 관리 지원이 제한됩니다.

- Microsoft Endpoint Manager에서 RealWear 장치 관리에 대한 자세한 내용을 보려면 [Intune에서 Android 장치 관리자 등록](/mem/intune/enrollment/android-enroll-device-administrator)을 참조하세요.
- 정책에 대한 자세한 내용은 [Google 모바일 서비스가 없는 환경에서 Intune을 사용하는 방법](/mem/intune/apps/manage-without-gms)을 참조하세요.

### <a name="third-party-enterprise-mobility-managers-emms"></a>타사 EMM(Enterprise Mobility Manager)

타사 EMM에 대한 지침은 [지원되는 엔터프라이즈 이동성 관리 공급자](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/)를 참조하세요.

## <a name="end-user-content"></a>최종 사용자 콘텐츠

최종 사용자 관점에서 이에 대한 자세한 내용은 [RealWear용 Microsoft Teams 사용](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f)을 참조하세요.