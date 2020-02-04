---
title: Microsoft 팀의 데이터 위치
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: anach, kehardy
description: Microsoft 팀에서 데이터가 저장 되는 위치에 대해 알아봅니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24432b0854ac0c4256f5d097bacfca5f1a392d72
ms.sourcegitcommit: 2cb46af39a0d116e8fd020aa04bd2ecbd6998a5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41679044"
---
# <a name="location-of-data-in-microsoft-teams"></a>Microsoft 팀의 데이터 위치

팀의 데이터는 Office 365 테 넌 트와 연결 된 지리적 영역에 위치 합니다. 현재, 팀은 오스트레일리아, 캐나다, 프랑스, 독일, 인도, 일본, 남아프리카, 대한민국, 스위스 (리히텐슈타인 포함), 미국, 호주, 영국, 미국, APAC, EMEA 지역 등을 지원 합니다. 

> [!IMPORTANT]
> 현재 팀은 오스트레일리아, 캐나다, 프랑스, 독일, 인도, 일본, 미국 아랍, 영국, 대한민국, 남아프리카, 스위스 (리히텐슈타인 포함) 새 테 넌 트에만 데이터 영주권을 제공 합니다.
> 새 테 넌 트가 테 넌 트에서 팀에 로그인 한 사용자가 없는 모든 테 넌 트로 정의 됩니다. 오스트레일리아, 인도, 일본, 대한민국의 기존 테 넌 트는 계속 해 서 자신의 팀 데이터를 APAC 지역에 저장 합니다. 캐나다의 기존 테 넌 트는 계속 해 서 해당 데이터를 미주에 저장 합니다. 프랑스, 독일, 리히텐슈타인, 미국 아랍, 영국, 남아프리카, 스위스의 기존 테 넌 트는 EMEA 지역에 저장 된 데이터를 갖습니다.

## <a name="where-your-teams-data-is-stored"></a>팀 데이터가 저장 되는 위치

테 넌 트에 대 한 데이터가 들어 있는 영역을 확인 하려면 [Microsoft 365 관리 센터](https://portal.office.com/adminportal/home) > **설정** > **조직 프로필로**이동 합니다. 아래로 스크롤하여 **데이터 위치로**이동 합니다.

![관리 센터의 팀을 비롯 한 데이터 위치 표 스크린샷](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="location-of-teams-data-at-rest"></a>팀 데이터의 남은 위치

팀 데이터는 콘텐츠 형식에 따라 다르게 저장 됩니다. 

![팀 콘텐츠 형식 및 나머지 위치에서 저장 되는 위치를 보여 주는 다이어그램](media/location-of-data-storage-at-rest.png)

자세한 내용은 [Microsoft 팀 아키텍처의 Ignite 브레이크 아웃 세션](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) 을 참조 하세요.

### <a name="core-teams-customer-data"></a>핵심 팀 고객 데이터

테 넌 트가 오스트레일리아, 캐나다, 유럽 연합, 프랑스, 독일, 인도, 일본, 남아프리카, 대한민국, 스위스 (리히텐슈타인 포함), 미국, 영국 또는 미국, Microsoft 상점 해당 위치 내 에서만 남은 고객 데이터는 다음과 같습니다.

- 팀 채팅, 팀 및 채널 대화, 이미지, 보이스 메일 메시지, 연락처
- SharePoint Online 사이트 콘텐츠 및 해당 사이트에 저장 된 파일
- 비즈니스용 OneDrive에 업로드 된 파일

#### <a name="chat-channel-messages-team-structure"></a>채팅, 채널 메시지, 팀 구조

팀의 모든 팀은 Office 365 그룹과 해당 SharePoint 사이트 및 Exchange 사서함에서 지원 됩니다. 개인 채팅 (그룹 채팅 포함), 채널에서 대화의 일부로 전송 된 메시지, 팀 및 채널의 구조는 Azure에서 실행 되는 채팅 서비스에 저장 됩니다. 정보 보호 기능을 사용 하도록 설정 하기 위해 사용자 및 그룹 사서함의 숨겨진 폴더에도 데이터가 저장 됩니다.

#### <a name="voicemail-and-contacts"></a>보이스 메일 및 연락처

보이스 메일 Exchange에 저장 됩니다. 연락처는 Exchange 기반 클라우드 데이터 저장소에 저장 됩니다. Exchange 및 Exchange 기반 클라우드 저장소는 전세계의 모든 데이터 센터 geos에서 데이터 영주권를 이미 제공 합니다. 모든 팀에 대해 오스트레일리아, 캐나다, 프랑스, 독일, 인도, 일본, 아랍에미리트, 영국, 미국, 영국, 남아프리카, 대한민국, 스위스 (리히텐슈타인 포함) 및 미국에 대 한 음성 및 연락처가 국가에 저장 됩니다. 다른 모든 국가의 경우 파일은 테 넌 트 선호도에 따라 미국, 유럽 또는 아시아 태평양 장소에 저장 됩니다.

#### <a name="images-and-media"></a>이미지 및 미디어

채팅에 사용 되는 미디어 (저장 되지 않고 원본 Giphy 서비스 URL에 대 한 참조 링크 인 Giphy Gif는 제외)는 채팅 서비스와 같은 위치에 배포 된 Azure 기반 미디어 서비스에 저장 됩니다.

#### <a name="files"></a>파일

채널의 누군가가 공유 하는 파일 (OneNote 및 위 키 포함)이 팀의 SharePoint 사이트에 저장 됩니다. 개인 채팅 또는 모임 또는 통화 중에 공유 된 파일은 파일을 공유 하는 사용자의 비즈니스 계정에 대 한 OneDrive에 업로드 되 고 저장 됩니다. Exchange, SharePoint 및 OneDrive는 전세계의 모든 데이터 센터 geos에서 데이터 영주권를 이미 제공 합니다. 따라서 기존 고객의 경우 팀 환경의 일부인 모든 파일, OneNote 전자 필기장, 팀 위 키 내용, 사서함,이 테 넌 트 선호도에 따라 위치에 이미 저장 되어 있습니다. 파일은 오스트레일리아, 캐나다, 프랑스, 독일, 인도, 일본, 아랍에미리트, 미국, 영국, 남아프리카, 대한민국, 스위스 (리히텐슈타인 포함)로 국가별에 저장 됩니다. 다른 모든 국가의 경우 파일은 테 넌 트 선호도에 따라 미국, 유럽 또는 아시아 태평양 장소에 저장 됩니다.

### <a name="datacenter-locations"></a>데이터 센터 위치

이 섹션에 설명 된 팀 서비스는 다음 위치에 나머지 데이터를 저장 합니다.

|국가 또는 지역  |데이터 센터 위치 |
|---------|---------|
|오스트레일리아   |새로운 남아프리카 웨일스 및 Victoria         |
|캐나다    |퀘벡에서 구/군/시         |
|프랑스    |Marseille 및 파리         |
|독일    |베를린 및 Frankfurt      |
|인도   |Chennai 및 Pune        |
|일본    |도쿄 (Saitama) 및 오사카         |
|리히텐슈타인   |Geneva 및 Zurich       |
|남아프리카 공화국     |요하네스버그 및 카보베르데         |
|대한민국     |서울 및 Busan         |
|스위스    |Geneva 및 Zurich       |
|아랍 에미리트 연합국     |아부다비 및 두바이         |
|영국     | Cardiff 및 런던        |
|미주-북쪽 및 남부 (AMER) |베이, CA, Boydton, VA       |
|아시아 태평양 (APAC)  |싱가포르 및 홍콩 특별 행정구        |
|유럽/중동, 아시아 (EMEA)   |더블린 및 암스테르담        |

> [!NOTE]
> 리히텐슈타인의 경우 데이터는 Geneva 및 Zurich의 스위스 데이터 센터에 나머지 위치에 저장 됩니다.

### <a name="data-stored-with-a-third-party-storage-provider"></a>타사 저장소 공급자에 저장 된 데이터

타사 저장소 공급자를 사용 하 여 파일을 저장할 수 있도록 허용 하는 조직은 해당 서비스의 저장소 위치에 따라 달라 지므로 해당 서비스에 대 한 나머지 데이터 위치를 별도로 검토 해야 합니다.

- **탭**: 탭을 통해 사용자는 앱 및 서비스에서 채널에 정보를 고정할 수 있습니다. 따라서 데이터는 저장 된 탭의 유형에 따라 달라 집니다. 탭 자체에는 데이터가 저장 되지 않습니다. 예를 들어 SharePoint 탭은 SharePoint 사이트 컬렉션이 프로 비전 된 위치에 따라 데이터를 저장 합니다. 파트너의 정보를 포함 하는 탭은 파트너가 사용 하는 시스템에 데이터를 직접 저장 하 고 보기만 표시 합니다.
- **다른 파트너 앱**: Microsoft는 팀 경험 내에서 사용할 수 있는 파트너의 앱 및 서비스에 대 한 데이터 영주권 지원 기능을 제공 하지 않습니다. 해당 솔루션의 정보를 직접 검토 하 여 데이터가 저장 되는 위치를 알아봅니다.

## <a name="see-also"></a>참고 항목

- [Microsoft 팀이 미국 아랍 데이터 영주권을 시작 합니다.](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-United-Arab-Emirates-Data-Residency/ba-p/980330)

- [Microsoft 팀이 동남 영주권 데이터를 시작 합니다.](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)

- [Microsoft 팀이 남아프리카 데이터 영주권을 시작 합니다.](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)

- [Microsoft 팀이 프랑스 데이터 영주권을 실행 합니다.](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)

- [Microsoft 팀은 인도 데이터 영주권를 시작 하 고 다른 geos는 곧 출시 됩니다.](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-India-Data-Residency-other-geos-coming/ba-p/154083)

- [Microsoft 팀이 오스트레일리아와 일본 데이터 영주권을 시작 합니다.](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)

- [Microsoft 팀은 캐나다 데이터 영주권, 오스트레일리아 및 일본 출시 예정](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)
