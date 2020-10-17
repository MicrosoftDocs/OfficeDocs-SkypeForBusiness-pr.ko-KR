---
title: Microsoft Teams의 데이터 위치
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: anach, kehardy
description: 이 문서에서는 Microsoft Teams에서 데이터가 지리적으로 어디에 위치하는지 알 수 있습니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c16065a864ac82cdf5f11c0d2c8254b648731cac
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121688"
---
# <a name="location-of-data-in-microsoft-teams"></a>Microsoft Teams의 데이터 위치

Teams의 데이터는 Microsoft 365 또는 Office 365 조직과 연결된 지리적 영역에 위치합니다. 현재 Teams는 오스트레일리아, 캐나다, 프랑스, 독일, 인도, 일본, 남아프리카 공화국, 대한민국, 스위스(리히텐슈타인 포함), 아랍에미리트, 영국, 미주, APAC 및 EMEA 지역을 지원합니다. 

> [!IMPORTANT]
> Teams는 현재 오스트레일리아, 캐나다, 프랑스, 독일, 인도, 일본, 아랍에미리트, 영국, 대한민국, 남아프리카 공화국, 스위스(리히텐슈타인 포함)의 신규 테넌트에 대한 데이터 보존을 제공합니다.
> 신규 테넌트는 Teams에 로그인한 사용자가 없는 모든 테넌트를 뜻합니다. 오스트레일리아, 인도, 일본, 대한민국의 기존 테넌트의 경우 Teams 데이터가 APAC 지역에 계속 저장됩니다. 캐나다의 기존 테넌트는 계속해서 해당 데이터를 미주에 저장합니다. 프랑스, 독일, 리히텐슈타인, 아랍에미리트, 영국, 남아프리카 공화국, 스위스의 기존 테넌트의 경우 데이터가 EMEA 지역에 저장됩니다.

## <a name="where-your-teams-data-is-stored"></a>Teams 데이터가 저장되는 위치

테넌트의 데이터가 저장되는 지역을 보려면 [Microsoft 365 관리 센터](https://portal.office.com/adminportal/home) > **설정** > **조직 프로필**로 이동하세요. **데이터 위치**로 스크롤 합니다.

![관리 센터에서 Teams를 포함하는 데이터 위치 테이블의 스크린샷](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="location-of-teams-data-at-rest"></a>Teams의 미사용 데이터 위치

Teams 데이터는 콘텐츠 형식에 따라 다르게 저장됩니다. 

![Teams 콘텐츠 형식과 미사용 상태로 저장된 위치를 보여주는 다이어그램](media/location-of-data-storage-at-rest.png)

자세한 내용은 Microsoft Teams 아키텍처의 [Ignite 브레이크아웃 세션](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071)을 참조하세요.

### <a name="core-teams-customer-data"></a>핵심 Teams의 고객 데이터

테넌트가 오스트레일리아, 캐나다, 유럽 연합, 프랑스, 독일, 인도, 일본, 남아프리카 공화국, 대한민국, 스위스(리히텐슈타인 포함), 아랍에미리트, 영국, 미국을 포함하는 경우 Microsoft는 다음과 같은 미사용 고객 데이터를 해당 위치에만 저장합니다.

- Teams 채팅, 팀과 채널 대화, 이미지, 음성 메일 메시지 및 연락처
- SharePoint 온라인 사이트 콘텐츠와 해당 사이트에 저장된 파일
- 비즈니스용 OneDrive에 업로드된 파일

#### <a name="chat-channel-messages-team-structure"></a>채팅, 채널 메시지, 팀 구조

Teams 내 모든 팀은 Microsoft 365 그룹 및 해당 SharePoint 사이트, 그리고 Exchange 사서함에 의해 지원됩니다. 비공개 채팅(그룹 채팅 포함), 채널 내 대화의 일부로 전송된 메시지, 그리고 팀과 채널 구조 또한 Azure에서 실행되는 채팅 서비스에 저장됩니다. 데이터는 정보 보호 기능을 위해 사용자 및 그룹 사서함의 숨겨진 폴더에도 저장됩니다.

#### <a name="voicemail-and-contacts"></a>음성 메일 및 연락처

음성 메일은 Exchange에 저장됩니다. 연락처는 Exchange 기반 클라우드 데이터 저장소에 저장됩니다. Exchange와 Exchange 기반 클라우드 스토어는 이미 전세계 데이터 센터 위치에 각각 데이터 보존을 제공하고 있습니다. 모든 팀의 경우 음성 메일과 연락처가 오스트레일리아, 캐나다, 프랑스, 독일, 인도, 일본, 아랍에미리트, 영국, 남아프리카 공화국, 대한민국, 스위스 (리히텐슈타인 포함) 및 미국에 저장됩니다. 기타 국가들의 경우 테넌트 선호도에 따라 파일이 미국, 유럽 또는 아시아 태평양 지역에 저장됩니다.

#### <a name="images-and-media"></a>이미지와 미디어

채팅에 사용 되는 미디어(저장 되지 않은 Giphy GIF를 제외하고, 원본 Giphy 서비스 URL의 참조 링크. Giphy는 Microsoft 서비스가 아님.)는 채팅 서비스와 동일한 위치에 배포되는 Azure 기반 미디어 서비스에 저장됩니다.

#### <a name="files"></a>파일

채널에서 다른 사람이 공유하는 파일(OneNote와 Wiki 포함)은 팀의 SharePoint 사이트에 저장됩니다. 비공개 채팅 또는 모임 또는 통화 중 채팅에서 공유된 파일은 파일을 공유 한 사용자의 비즈니스용 OneDrive에 업로드되고 저장됩니다. Exchange, SharePoint 및 OneDrive는 이미 전세계 데이터 센터 위치에 각각 데이터 보존을 제공하고 있습니다. 따라서 기존 고객의 경우 Teams 경험의 일부인 모든 파일, OneNote 노트북, Teams 위키 콘텐츠와 사서함이 이미 테넌트 선호도에 따른 위치에 저장되고 있습니다. 파일은 오스트레일리아, 캐나다, 프랑스, 독일, 인도, 일본, 아랍에미리트, 영국, 남아프리카 공화국, 대한민국, 스위스(리히텐슈타인 포함) 국내에 저장됩니다. 기타 국가들의 경우 테넌트 선호도에 따라 파일이 미국, 유럽 또는 아시아태평양 지역에 저장됩니다.

### <a name="datacenter-locations"></a>데이터 센터 위치

이 섹션에 설명된 Teams 서비스는 아래와 같은 위치에 미사용 데이터를 저장합니다.

|국가 또는 지역  |데이터센터 위치 |
|---------|---------|
|오스트레일리아   |뉴사우스웨일스 및 빅토리아         |
|캐나다    |퀘벡 시티 및 토론토         |
|프랑스    |마르세유 및 파리         |
|독일    |베를린 및 프랑크푸르트      |
|인도   |첸나이 및 푼        |
|일본    |도쿄(사이타마) 및 오사카         |
|리히텐슈타인   |제네바 및 취리히       |
|남아프리카 공화국     |요하네스버그 및 케이프타운         |
|대한민국     |서울 및 부산         |
|스위스    |제네바 및 취리히       |
|아랍에미리트     |아부다비 및 두바이         |
|영국     | 카디프 및 런던        |
|미주-북부 및 남부(AMER) |캘리포니아 베이 및 버지니아 보이드턴       |
|아시아 태평양(APAC)  |싱가포르 및 홍콩 특별행정구        |
|유럽, 중동 및 아시아(EMEA)   |더블린 및 암스테르담        |

> [!NOTE]
> 리히텐슈타인의 경우 데이터가 미사용 상태로 제네바 및 취리히에 위치한 스위스 데이터 센터에 저장됩니다.

### <a name="data-stored-with-a-third-party-storage-provider"></a>제3자 저장소 공급자에 저장되는 데이터

사용자가 제3자 저장소 공급자를 이용하여 파일을 저장할 수 있도록 허용 하는 조직의 경우, 해당 서비스의 저장소 위치에 종속되므로 해당 서비스에 대한 미사용 데이터의 위치를 별도로 검토해야 합니다.

- **탭**: 탭은 사용자가 앱 및 서비스의 정보를 채널에 고정할 수 있도록 합니다. 따라서 데이터가 저장되는 탭 유형에 따라 달라집니다. 탭 자체는 데이터를 저장하지 않습니다. 예를 들어 SharePoint 탭의 경우 SharePoint 사이트 모음을 포함하는 위치에 따라 데이터를 저장합니다. 파트너의 정보를 포함하는 탭은 파트너가 사용하는 시스템에 데이터를 바로 저장하고 보기만 표시합니다.
- **기타 파트너 앱**: Microsoft는 Teams 환경 내에서 사용할 수 있는 파트너 제공 앱 및 서비스에 대한 데이터 보존을 지원하지 않습니다. 해당 솔루션의 정보를 직접 검토하여 데이터가 저장되는 위치를 알아보세요.

## <a name="see-also"></a>참고 항목

- [Microsoft Teams에서 아랍에미리트의 데이터 보존을 시작합니다](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-United-Arab-Emirates-Data-Residency/ba-p/980330)

- [Microsoft Teams에서 대한민국의 데이터 보존을 시작합니다](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)

- [Microsoft Teams에서 남아프리카 공화국의 데이터 보존을 시작합니다](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)

- [Microsoft Teams에서 프랑스의 데이터 보존을 시작합니다](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)

- [Microsoft Teams에서 인도의 데이터 보존을 시작하고 기타 지역에서도 곧 시작할 예정입니다](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-India-Data-Residency-other-geos-coming/ba-p/154083)

- [Microsoft Teams에서 오스트레일리아 및 일본의 데이터 보존을 시작합니다](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)

- [Microsoft Teams에서 캐나다 데이터 보존을 시작하고 곧 오스트레일리아 및 일본에서도 시작할 예정입니다](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)
