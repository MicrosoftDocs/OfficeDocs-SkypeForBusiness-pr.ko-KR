---
title: Microsoft Teams에서 스트림 만들기
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: asteele
search.appverid: MET150
f1.keywords:
- NOCSH
description: 이 문서에서는 Microsoft Teams 스트리밍 이벤트에 대한 스트림을 만드는 방법을 안내합니다.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: b7ff5d15a08f186ae59ccef65fcd8280d84237d1
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767992"
---
# <a name="create-a-live-event-in-microsoft-teams"></a>Microsoft Teams에서 라이브 이벤트 만들기

> [!IMPORTANT]
> **중국**: 현재 중국에 있는 사용자는 IT 관리자의 도움 없이는 Microsoft Teams 또는 Yammer 라이브 이벤트를 설정하거나 참석하거나 주문형 비디오를 볼 수 없습니다.
>
> 시작하기 전에 관리자에게 확인하여 조직에서 이러한 앱이 원활하게 작동할 수 있도록 회사 네트워크를 연결하기 위해 VPN을 설정해야 하는지 확인합니다.

> [!IMPORTANT]
> 라이브 이벤트를 설정할 때 최상의 환경을 위해 이벤트 최소 24시간 전에 비디오, 커뮤니티 및 사용자 권한을 구성하는 것이 좋습니다. 여기에는 사용자 추가, 비디오 권한 업데이트 및 커뮤니티를 비공개에서 퍼블릭으로 변경하는 등의 설정이 포함됩니다. 특정 변경 내용이 Microsoft Stream, Microsoft Teams 및 Microsoft Yammer에 전파되려면 최대 2시간이 걸릴 수 있습니다. 24시간 이상을 허용하면 필요한 경우 테스트하고 조정하는 시간을 제공할 수 있습니다.

## <a name="schedule-the-live-event"></a>라이브 이벤트 예약

1. Microsoft Teams 클라이언트를 열고 일정으로 이동합니다.
1. **새 모임** 드롭다운을 사용합니다.
1. **라이브 이벤트** 옵션을 선택합니다.
1. **새 라이브 이벤트** 팝업 창에서 왼쪽에 이벤트 세부 정보(**제목**, **위치**, **시작**, **종료**, **표준 시간대** 및 **세부 정보**)를 입력합니다.
1. 같은 페이지의 오른쪽에서 **발표자를 개별적으로** 또는 그룹을 통해 발표자와 프로듀서를 추가하도록 초대합니다.
1. 모든 항목이 입력되면 **다음** 을 선택합니다.
1. 라이브 이벤트를 시청할 수 있는 사용자를 지정하려면 **라이브 이벤트 권한** 으로 **사람 및 그룹**, **조직 전체** 또는 **공용** 을 선택합니다.
1. **라이브 이벤트를 생성하려면 어떻게** 할까요? 아래에서 **Teams 인코더(미리 보기)** 를 선택합니다.
1. 이벤트 옵션에서 **Q&A**, 캡션 등과 같은 필수 **옵션을** 구성 **합니다**.
1. **일정을** 선택하여 라이브 이벤트에 대한 예약을 완료합니다.

## <a name="stream-the-live-event"></a>라이브 이벤트 스트리밍

1. 라이브 이벤트를 예약하면 일정 초대의 **RTMP 세부 정보** 섹션에서 **RTMP 서버 수집 URL** 및 **RTMP 키를** 검색할 수 있습니다. 이 섹션은 인코더에서 RTMP 수집을 통해 콘텐츠를 푸시하는 데 사용할 수 있습니다.
1. 인코더를 설정하려면 RTMP 수집 URL 및 RTMP 키를 인코더에 복사하여 라이브 인코더 피드를 Team에 보내기 시작합니다. Microsoft Teams에서 라이브 스트리밍에 인코더를 사용하는 방법에 대한 자세한 정보가 있습니다.
1. Microsoft Teams 클라이언트를 사용하여 라이브 이벤트를 생산자로 참가합니다. 자세한 내용은 > 모임 옵션에서 RTMP를 찾을 수도 있습니다.
1. 인코더에서 서버 수집 지점으로 콘텐츠를 푸시하기 시작하면 생산자 미리 보기 업데이트가 표시됩니다.
1. 설정에 만족하고 생산자 UI에서 미리 보기를 볼 수 있으면 원본에서 **RTMP 피드** 를 선택하고 **라이브로 보내기** 를 선택합니다.
1. **이벤트 시작을** 선택하여 라이브 이벤트를 시작하고 대상 그룹 구성원이 이벤트를 볼 수 있는 게시물을 게시합니다.
1. 이벤트를 마쳤으면 생산자 UI에서 **이벤트 종료** 를 선택합니다. 이렇게 하면 이벤트가 종료되고 주문형 비디오에 콘텐츠를 즉시 사용할 수 있습니다.

라이브 이벤트 스트리밍에 대한 자세한 내용은 [Teams 인코더를 사용하여 라이브 이벤트 생성을 참조하세요](https://support.microsoft.com/office/produce-a-teams-live-event-using-teams-encoder-b0026c9d-fd37-4bb3-bffc-6961f221fbe9).
