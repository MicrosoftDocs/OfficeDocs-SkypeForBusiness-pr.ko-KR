---
title: Microsoft Teams에 얼리 어답터 등록
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.date: 11/06/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: serdars
description: Microsoft Teams에서 만든 팀과 채널의 첫 번째 집합에 얼리 어답터를 등록하는 방법을 알아보세요.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- seo-marvel-apr2020
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45ffd7a36d128e8b64ecc2726e4562b96e42fbfb
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777518"
---
# <a name="onboard-early-adopters-to-microsoft-teams"></a>Microsoft Teams에 얼리 어답터 등록

## <a name="invite-users-to-teams"></a>Teams에 사용자 초대

사용자가 만든 팀의 이름과 설명을 사용하여 사용자에게 환영 전자 메일을 보내고 Teams의 대화에 참여하도록 초대합니다. Teams 클라이언트, 교육 및 지원을 받을 수 있는 위치를 알 수 있도록 전자 메일에 다음 링크를 포함해야 합니다.
- [Teams 웹 클라이언트](https://teams.microsoft.com)
- [데스크톱 및 모바일 클라이언트 다운로드 링크](https://teams.microsoft.com/downloads)
- [Teams 교육 비디오](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [Teams 도움말 문서](https://support.office.com/teams)

예를 들어, "Teams 소개" 팀의 경우 다음과 같이 전자 메일을 시작하는 것이 좋습니다.

   ```console
   Welcome to Microsoft Teams for <insert_company_name>. Teams is a chat-based workspace that brings together chat, files, people, and tools in one place. 

   We created a team called "Get to know Teams" to get you started. Use it to experiment, ask questions, and discover the possibilities of Teams. 

   To join, click <link to the team>.
   ```

처음 참여하는 경우 사용자와 소통합니다. Teams에 환영 메시지를 게시하고 채널에서 채팅을 시작합니다. 이렇게 하면 톤이 설정되고 사용자가 Teams로 전환하도록 권장합니다. 환영 메시지에는 Teams를 가져올 수 있는 위치와 신속하게 실행하는 데 유용한 정보를 알 수 있도록 전자 메일에서 보낸 동일한 링크를 포함합니다. 사용자가 채팅을 시작하고, 파일을 공유하며, 서로 공동 작업할 수 있도록 Teams를 다운로드하여 설치하고 로그인하는 방법을 확인하기 위해 사용자와 연락합니다.  

## <a name="get-teams-clients"></a>Teams 클라이언트 가져오기
Teams에는 데스크톱(Windows 및 Mac), 웹 및 모바일(iOS 및 Android)용 클라이언트가 있습니다. Teams에서 최상의 환경을 사용하기 위해 데스크톱과 모바일 클라이언트를 설치하는 것이 좋습니다. 

이동: [Windows용 Teams](#teams-for-windows) | [Mac용 Teams](#teams-for-mac) | [웹 브라우저용 Teams](#web-client) | [iOS용 Teams](#teams-for-ios) | [Android용 Teams](#teams-for-android)

### <a name="desktop-client"></a>데스크톱 클라이언트

Teams 데스크톱 클라이언트는 Windows 및 Mac 사용자에게 최고의 전체 환경을 제공합니다. 자세한 내용은 [Teams용 클라이언트 가져오기(데스크톱 클라이언트)](./get-clients.md#desktop-client) 및 [Microsoft Teams 앱의 하드웨어 요구 사항](./hardware-requirements-for-the-teams-app.md)을 참조하세요.

> [!NOTE]
> 관리자는 이 방법을 선택하여 Microsoft Endpoint Configuration Manager(Windows) 또는 Jamf Pro(macOS)와 같은 설치 파일을 조직의 컴퓨터에 배포할 수 있습니다.

#### <a name="teams-for-windows"></a>Windows용 Teams 
Windows 데스크톱 클라이언트를 가장 간편하게 설치하는 방법은 다음과 같습니다.

1. [https://teams.microsoft.com/downloads](https://teams.microsoft.com/downloads)에서 Windows 데스크톱 클라이언트를 다운로드합니다.
2. 설치 관리자를 실행합니다(관리자 권한이 필요하지 않음). 
3. 설치가 완료된 후 Teams를 시작합니다.

> [!NOTE]
> 나중에, 조직 전체에 보다 공식적으로 Teams를 대량 배포해야 하는 경우 [Teams Windows 데스크톱 클라이언트](https://aka.ms/teams-clients) 비디오를 확인하여 계획하고 배포하는 방법에 대해 알아보세요. 

#### <a name="teams-for-mac"></a>Mac용 Teams 
Mac 데스크톱 클라이언트를 가장 간편하게 설치하는 방법은 다음과 같습니다.

1. [https://teams.microsoft.com/downloads](https://teams.microsoft.com/downloads)에서 Mac 데스크톱 클라이언트를 다운로드합니다.
2. 설치 관리자를 실행합니다(관리자 권한이 필요함). 
3. 설치가 완료된 후 Teams를 시작합니다.

### <a name="web-client"></a>웹 클라이언트
Teams에서 다양한 브라우저를 지원하며 기능이 풍부한 웹 클라이언트 [https://teams.microsoft.com](https://teams.microsoft.com)을 제공합니다.

[!INCLUDE [browser-support](includes/browser-support.md)]

### <a name="mobile-client"></a>모바일 클라이언트

iOS 및 Android용 Teams 모바일 클라이언트를 사용하면 이동 중에도 연결하여 작업할 수 있습니다. 자세한 내용은 [Teams용 클라이언트(모바일 클라이언트) 가져오기](./get-clients.md#mobile-clients)를 참조하세요.

#### <a name="teams-for-ios"></a>iOS용 Teams 

iOS 10.0 이상을 실행하는 사용자는 Apple 앱 스토어에서 Teams 모바일 앱을 다운로드하여 바로 시작할 수 있습니다.  

#### <a name="teams-for-android"></a>Android용 Teams 
Android 4.4 이상을 실행하는 사용자는 Google Play 스토어에서 Teams 모바일 앱을 다운로드하여 바로 시작할 수 있습니다.  

## <a name="drive-initial-adoption"></a>초기 채택률 증가

새 공동 작업 환경을 촉진하고 Teams 챔피언를 개발하는 데 Teams를 적극적으로 사용하도록 얼리 어답터에게 장려하는 것이 중요합니다. 채택율을 높이기 위해 사용자와 지침을 공유하는 데 "Teams 소개" 팀에서 사용자가 만든 “어떻게 하나요” 채널을 사용하는 것이 좋습니다. 

조직에 대한 Teams 채택 증가에 대한 자세한 지침은 [Teams 채택](adopt-microsoft-teams-landing-page.md)을 참조하세요.

## <a name="next-steps"></a>다음 단계
[사용 현황 및 피드백 모니터링](get-started-with-teams-monitor-usage-and-feedback.md)으로 이동