---
title: Microsoft Teams에 대한 정책 컨트롤 개요
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Microsoft Teams에 대한 정책 컨트롤 개요입니다.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f642b1ce9a767c30077374aa193355edbbbef09
ms.sourcegitcommit: 2591c96d8613660220c5af71fc945e27b31175d7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52863219"
---
# <a name="policy-control-overview-for-microsoft-teams"></a>Microsoft Teams에 대한 정책 컨트롤 개요

Microsoft는 사용자가 Microsoft 365의 일부인 Microsoft Teams를 사용할 때 데이터 수집 및 사용 방법에 관해 선택해야 하는 정보와 컨트롤을 사용자에게 제공하기 위해 최선을 다하고 있습니다.

이 문서에서는 다음 영역에 대한 개인 정보 컨트롤에 대한 정보를 제공합니다.

- 사용자의 조직에서 Windows를 실행하는 컴퓨터에서 사용되는 Teams 및 Office 소프트웨어에 관해 수집되어 Microsoft에 전송되는 **진단 데이터**.
- 클라우드 기반 기능을 사용하여 향상된 Teams 및 Office 기능을 제공하는 **연결된 환경**.

이 변경에는 새롭게 업데이트된 UI(사용자 인터페이스) 요소 및 정책 설정이 있습니다.

> [!IMPORTANT]
> 자세한 내용은 Microsoft 365 대한 [정책 제어 개요](/deployoffice/privacy/overview-privacy-controls) 콘텐츠를 검토하세요.

## <a name="diagnostic-data-sent-from-microsoft-365-apps-for-enterprise-to-microsoft"></a>엔터프라이즈용 Microsoft 365 앱에서 Microsoft로 보낸 진단 데이터

진단 데이터는 다음과 같은 경우에 사용됩니다.

- Teams를 안전하고 최신 상태로 유지하세요.
- 문제를 검색하고 진단하며 교정합니다.
- 제품을 개선합니다.

수집된 데이터 중 일부에는 다음이 포함됩니다.

- 응용 프로그램 언어
- 사용자 유형
- OS의 빌드 버전

## <a name="clients-that-adhere-to-diagnostic-controls"></a>진단 컨트롤을 준수하는 클라이언트

다음 클라이언트는 진단 컨트롤을 준수하고 데이터를 제출합니다.

- iOS
- Android
- 데스크톱(win32 API를 사용하는 구성 요소만 해당)

필수 진단 데이터 이벤트 및 해당 속성 목록을 보려면 다음 문서를 참조하세요.

- [Microsoft Teams의 필수 모바일 진단 데이터](policy-control-diagnostic-data-mobile.md)
- [Microsoft Teams의 필수 데스크톱 진단 데이터](policy-control-diagnostic-data-desktop.md)

## <a name="diagnostic-data-sent-from-the-teams-app-to-microsoft"></a>Teams 앱에서 Microsoft로 보낸 진단 데이터

이 진단 데이터는 사용자의 조직에서 Windows를 실행하는 컴퓨터에서 사용되는 Teams 소프트웨어에 관해 수집되어 Microsoft에 전송됩니다.

사용자가 선택할 수 있는 Teams 소프트웨어를 위한 진단 데이터의 3가지 수준은 다음과 같습니다.

- **필수** Office를 보호하고, 최신 상태로 유지하며, Office가 설치된 디바이스에서 기대되는 성능을 유지하는 데 필요한 최소한의 데이터.
- **선택 사항** 제품을 개선하고 향상된 정보를 제공하여 문제를 감지, 진단, 해결하는 데 도움이 되는 추가 데이터.
- **모두 아님** 사용자의 디바이스에서 실행되는 Teams 소프트웨어에 관해 수집되고 전송되는 진단 데이터 없음. 그러나 이 옵션은 사용자가 Teams를 사용하며 겪을 수 있는 문제를 감지, 진단, 해결하는 기능을 상당히 제한합니다.

필수 진단 데이터에는 디바이스에 설치된 Teams 클라이언트의 버전 정보 또는 모임에 참여할 때 Teams 응용 프로그램이 충돌함을 나타내는 정보 등이 포함될 수 있습니다. 선택적 진단 데이터에는 전화를 시작하는 데 걸리는 시간에 관한 정보가 포함될 수 있으며, 이 정보는 연결 또는 네트워크 성능에 발생하는 특정 문제를 나타낼 수 있습니다.

선택 사항 진단 데이터를 보내시는 경우 필수 진단 데이터도 함께 보내야 합니다.

조직의 관리자는 정책 설정을 사용하여 Microsoft에 보낼 진단 데이터 수준을 선택할 수 있습니다. 이 설정을 변경하지 않는 한 Microsoft에는 선택 사항 진단 데이터가 전송됩니다. 선택 사항 진단 데이터를 제공하면 Microsoft의 엔지니어링 팀이 더 효과적으로 문제를 감지, 진단, 완화하여 조직에게 미치는 영향을 줄일 수 있습니다. 

전송되는 진단 데이터 수준을 선택하려면 [Office 클라우드 정책 서비스](/deployoffice/overview-office-cloud-policy-service)를 사용하고 *Office에서 Microsoft 정책 설정으로 보내는 클라이언트 소프트웨어 진단 데이터의 수준 구성* 을 구성합니다. 이 작업은 엔터프라이즈용 Microsoft 365 앱과 함께 제공되는 다른 Office 앱(예: Word, Excel 및 PowerPoint)에서 보내는 진단 데이터 수준을 구성하는 데 사용되는 것과 동일한 정책 설정입니다.

사용자가 조직 자격 증명(때때로 회사 또는 학교 계정이라고 함)을 사용하여 Teams에 로그인한 경우 사용자는 자신의 디바이스 진단 데이터 수준을 변경할 수 없습니다.

이 진단 데이터에는 사용자 이름, 전자 메일 주소 또는 기타 사용자 콘텐츠(예: Teams에서 공유된 Office 파일, Teams에서 전송된 채팅 메시지 또는 Teams 채널에 게시된 게시물의 텍스트)가 포함되지 않습니다. Microsoft의 시스템은 사용자의 진단 데이터와 연결되는 고유의 ID를 만듭니다. 100회 충돌한 Teams 앱을 보여주는 진단 데이터를 받으면 이 고유 ID를 통해 단일 사용자에게서 100회 충돌이 발생했는지 또는 100명의 서로 다른 사용자에게서 각 1회씩 충돌이 발생했는지 확인합니다. Microsoft는 이 고유 ID를 사용하여 특정 사용자를 식별하지 않습니다.

Microsoft에 어떤 진단 데이터가 전송되는지 확인하려면 Microsoft Store에서 무료로 다운로드하여 설치할 수 있는 진단 데이터 뷰어를 사용하세요. 자세한 내용은 [Office로 진단 데이터 뷰어 사용](https://support.microsoft.com/topic/cf761ce9-d805-4c60-a339-4e07f3182855)을 참조하세요.

> [!NOTE]
> Android를 실행하는 장치에서 Teams에서 진단 데이터 뷰어 대한 지원을 사용할 수 있습니다. Windows, macOS 또는 iOS를 실행하는 장치에서 Teams 지원이 작동 중입니다.

## <a name="required-service-data-for-connected-experiences"></a>연결된 환경을 위한 필수 서비스 데이터

필수 서비스 데이터는 Microsoft가 클라우드 기반 연결된 환경을 제공하고 이 환경을 예상대로 보호하며 작동할 수 있도록 하는 데이터입니다. 이 기능을 제공하지 않도록 선택할 수 있으며, 이 경우에는 연결된 환경의 기능을 지원하기 위해 Microsoft에 이 정보를 제공하지 않습니다. [필수 서비스 데이터](/deployoffice/privacy/required-service-data)에 대한 자세한 정보를 확인할 수 있습니다.

## <a name="essential-services-for-microsoft-teams"></a>Microsoft Teams의 필수 서비스

또한 엔터프라이즈용 Microsoft 365 앱이 기능하는 방법에 필수적인 서비스 집합도 있으며 이 서비스 집합은 비활성화할 수 없습니다. 예를 들어 엔터프라이즈용 Microsoft 365 앱을 사용할 수 있도록 라이선스가 적절히 제공되었는지 확인하는 라이선싱 서비스가 있습니다. 이 서비스에 관한 필수 서비스 데이터는 구성한 정책 설정과는 관계없이 수집되어 Microsoft에 전송됩니다.

자세한 내용은 [Office의 필수 서비스](/deployoffice/privacy/essential-services)를 참조하세요.