---
title: AppLocker 제어 정책
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
description: AppLocker 애플리케이션 제어 정책을 사용하여 Teams 데스크톱 클라이언트 애플리케이션을 사용하도록 설정하는 방법을 배워야 합니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4e70fc4502851137494c316db9eff7faefc140d1
ms.sourcegitcommit: c573b0be535fcf927ae01d60a7eb8fbf1aec271d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46526694"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Microsoft Teams의 AppLocker 애플리케이션 제어 정책

이 문서에서는 AppLocker 애플리케이션 제어 정책을 사용하여 Teams 데스크톱 클라이언트 앱을 사용하도록 설정하는 방법을 설명하고 있습니다. AppLocker의 사용은 비관리자에 의해 프로그램 및 스크립트 실행을 제한하도록 디자인됩니다. AppLocker에 대한 자세한 내용은 [AppLocker란?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)

AppLocker에서 Teams를 사용하도록 설정하는 프로세스에는 AppLocker 기반 허용 목록 정책을 만들어야 합니다. 정책은 그룹 정책 관리 소프트웨어 및/또는 AppLocker용 Windows PowerShell cmdlet을 사용하여 만들어집니다(자세한 내용은 [AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) 기술 참조). AppLocker 정책은 XML 형식으로 저장되고 모든 텍스트 또는 XML 편집기로 편집할 수 있습니다.

## <a name="teams-allow-list-with-applocker"></a>AppLocker를 사용하여 Teams 허용 목록

AppLocker 규칙은 규칙 컬렉션으로 구성됩니다. AppLocker 규칙은 대상 앱에 적용하며 AppLocker 정책을 구성하는 구성 요소입니다.  

Teams를 허용하려면 모든 Teams [](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) 앱 파일이 디지털 서명되어 게시자 조건 규칙을 사용하는 것이 좋습니다.
  
Teams 설치 디렉터리는 사용자가 사용할 수 있기 때문에 경로 규칙을 사용하지 않는 것이 좋습니다. 또한 Teams 클라이언트 앱이 업데이트될 때마다 규칙을 업데이트해야 하기 때문에 해시 규칙을 사용하지 않는 것이 좋습니다.

Teams 데스크톱 실행 파일은 디지털 서명이 됐기 때문에 게시자 조건은 디지털 서명 및 포함된 버전 특성을 기반으로 앱 파일을 식별합니다. 디지털 서명에는 앱 파일(게시자)을 만든 회사에 대한 정보가 포함되어 있습니다. 이진 리소스에서 얻은 버전 정보에는 파일이 포함된 제품의 이름과 애플리케이션 파일의 버전 번호가 포함됩니다.

### <a name="example-of-publisher-condition-rules"></a>게시자 조건 규칙 예제

Teams 클라이언트 앱(모든 파일, 모든 버전)의 경우 DLL 규칙에 따라 실행 가능한 & 추가합니다.

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>관련 항목
[AppLocker란?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [AppLocker 기술 참조](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)
