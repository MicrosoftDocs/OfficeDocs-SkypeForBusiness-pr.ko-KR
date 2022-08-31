---
title: Teams 선택적 연결된 환경
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: ''
ms.localizationpriority: high
search.appverid: MET150
description: 이 문서에서는 Microsoft Teams에서 확인할 수 있는 선택적 연결된 환경에 관해 간략하게 설명합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03c23ccc1e9d24733f083c3e1d780b38138d366e
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396269"
---
# <a name="overview-of-optional-connected-experiences-in-microsoft-teams"></a>Microsoft Teams의 선택적 연결된 환경 개요

회사 또는 학교 계정을 사용하는 경우 조직의 관리자가 Microsoft Teams를 사용하는 동안 GIPHY 및/또는 URL 미리 보기 서비스와 같은 하나 이상의 클라우드 백업형 서비스(**선택적 연결된 환경** 이라고도 함)를 사용할 권한을 부여했을 수 있습니다. 이러한 클라우드 백업형 서비스는 선택 사항입니다. 이러한 서비스를 사용할지 여부는 사용자가 결정합니다. 각 선택적 서비스에 대해 별도로 설명된 대로 [Microsoft Online 서비스 약관과 다른 조건에](https://www.microsoft.com/licensing/product-licensing/products) 따라 사용자에게 제공됩니다. 이 문서에는 Teams 클라우드 백업형 서비스가 표시되어 이습니다.

관리자가 사용자에게 Teams에서 선택적 연결된 환경을 사용할 수 있는 기능을 부여한 경우 Teams의 **설정** > **개인 정보** 로 이동하여 선택적 연결된 환경을 사용할지 여부를 선택할 수 있습니다.

> [!NOTE]
> 관리자인 경우 사용자가 선택적 연결된 환경을 사용할 수있는 권한을 부여하거나 제한할 수 있습니다. 이 작업은 [Office 클라우드 정책 서비스](/deployoffice/overview-office-cloud-policy-service)를 사용하고 *Office에서 추가 선택적 연결된 환경 사용 허용* 정책 설정을 구성하여 수행할 수 있습니다. 이는 엔터프라이즈용 Microsoft 365 앱과 함께 제공되는 Office 앱(예: Word, Excel 및 PowerPoint)에서 사용자가 선택적 연결 환경을 사용할 수 있는지 여부를 제어하는 동일한 정책 설정입니다.

## <a name="giphy"></a>GIPHY

GIPHY는 Teams 채팅에 Gif를 사용할 수 있게 해 주는 클라우드 백업형 서비스입니다. **Teams** > **GIF** > **검색** 에 있는 경우 검색 용어가 GIPHY로 전송됩니다. 관리자가 허용하고 사용자가 사용하도록 선택한 경우, 이 환경은 [GIPHY 개인정보처리방침](https://support.giphy.com/hc/articles/360032872931-GIPHY-Privacy-Policy) 및 [서비스 약관](https://support.giphy.com/hc/articles/360020027752-GIPHY-User-Terms-of-Service)을 준수하게 됩니다.

:::image type="content" source="media/giphy-menu.png" alt-text="Giphy 이미지 또는 이미지를 검색하기 위해 정보를 입력하기 위한 Giphy 선택 단추와 텍스트 상자를 보여주는 메뉴입니다.":::

## <a name="url-preview-service"></a>URL 미리 보기 서비스

URL 미리 보기 서비스는 사용자가 URL 문자열을 보낼 때 미리 보기 코드 조각을 자동으로 생성하고 해당 URL 아래에 첨부합니다. 이 서비스는 사용자가 메시지를 입력하는 동안 서비스 URL에 요청을 생성합니다. 서비스 URL에 schema.org 데이터가 없는 경우 Bing 검색에 요청을 보내 미리 보기 조각을 생성하는 데 필요한 데이터를 가져옵니다. Bing에 의존하는 환경은 [Microsoft 서비스 계약의](https://www.microsoft.com/servicesagreement) 조건에 따라 사용자에게 라이선스가 부여되며 [개인정보처리방침](https://privacy.microsoft.com/privacystatement)의 적용을 받습니다. 이러한 서비스를 사용하는 동안 Microsoft Teams에 제공하는 모든 URL을 Microsoft Bing으로 보낼 수 있습니다. Bing 조직에서는 연결되지 않습니다.

:::image type="content" source="media/url-preview.png" alt-text="텍스트 상자에서 Microsoft 홈페이지 URL 미리 보기 샘플을 보여 주는 화면":::

## <a name="teams-apps-link-previews"></a>Teams 앱 링크 미리 보기

Teams 앱 링크 미리 보기 서비스는 앱의 적응형 카드의 미리 보기 조각을 생성하고 사용자가 Teams 스토어의 앱에 매핑되는 URL 문자열을 보낼 때 URL 아래에 연결합니다. 이 서비스는 사용자가 메시지를 입력하는 동안 서비스 URL에 요청을 생성합니다.

## <a name="teams-device-store-checkout"></a>Teams 디바이스 저장소 체크 아웃  

Teams 디바이스 저장소는 Teams 관리 센터에 있으며 Teams 인증 디바이스를 검색하고 구매할 수 있습니다. 체크 아웃을 사용하도록 설정하기 위해 Teams 디바이스 저장소는 사용자 이메일 주소, 사용자 GUID 및 테넌트 GUID를 포함한 기본 사용자 및 회사 정보를 UnifiedCommunications.com 공유합니다. Office  정책 설정 **에서 추가 선택적 연결 환경 사용을 허용하는** 경우 이 환경은 서비스 약관 및 UnifiedCommunications.com 개인정보처리방침의 적용을 받습니다.

:::image type="content" source="media/teams-device-store-buttons.png" alt-text="Teams 관리 센터에서 디바이스를 구매할 수 있도록 하는 타사 회사인 UnifiedCommunications.com 제공하는 체크 아웃 옵션이 포함된 Teams 디바이스 저장소 페이지의 일부 스크린샷":::

Teams 디바이스 저장소에 대한 자세한 내용은 다음을 확인하세요. [Teams 디바이스 저장소에서 디바이스 구매](devices/device-store.md)

## <a name="related-articles"></a>관련 기사

- [Teams에 관한 정책 제어 개요](policy-control-overview.md)
- [개인 정보 보호 및 Microsoft Teams](teams-privacy.md)
- [Office의 선택 사항 연결된 환경 개요](/deployoffice/privacy/optional-connected-experiences)
- [Office의 필수 서비스 데이터](/deployoffice/privacy/required-service-data)
- [계정 개인 정보 설정](https://support.microsoft.com/office/3e7bc183-bf52-4fd0-8e6b-78978f7f121b)
