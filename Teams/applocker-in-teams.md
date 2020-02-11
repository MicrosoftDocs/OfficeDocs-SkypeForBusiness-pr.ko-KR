---
title: Microsoft 팀의 AppLocker 응용 프로그램 제어 정책
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
description: AppLocker 응용 프로그램 제어 정책으로 팀 데스크톱 클라이언트 응용 프로그램을 사용 하도록 설정 하는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 13a1afd4ad4089db3c6b0c1223bf06831d9be667
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888557"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Microsoft 팀의 AppLocker 응용 프로그램 제어 정책

이 문서에서는 AppLocker 응용 프로그램 제어 정책으로 팀 데스크톱 클라이언트 앱을 사용 하도록 설정 하는 방법을 설명 합니다. AppLocker 사용은 관리자가 아닌 사용자가 프로그램과 스크립트 실행을 제한 하도록 설계 되었습니다. AppLocker에 대 한 자세한 내용 및 지침은 [applocker 란?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)을 참조 하세요.

AppLocker로 팀을 사용 하도록 설정 하는 프로세스에는 AppLocker 기반 whitelisting 정책을 만들어야 합니다. 정책은 그룹 정책 관리 소프트웨어 및/또는 AppLocker 용 Windows PowerShell cmdlet을 사용 하 여 생성 됩니다 (자세한 내용은 [applocker 기술 참조](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) 를 참조 하세요). AppLocker 정책은 XML 형식으로 저장 되며 모든 텍스트 또는 XML 편집기를 사용 하 여 편집할 수 있습니다.

## <a name="teams-whitelisting-with-applocker"></a>AppLocker로 whitelisting 팀

AppLocker 규칙은 규칙 모음으로 구성 됩니다. AppLocker 규칙은 대상 앱에 적용 되며 AppLocker 정책을 구성 하는 구성 요소입니다.  

팀을 허용 목록 모든 팀 앱 파일에 디지털 서명이 있으므로 [게시자 조건 규칙](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) 을 사용 하는 것이 좋습니다.
  
팀 설치 디렉터리는 사용자에 게 쓸 수 있으므로 경로 규칙을 사용 하지 않는 것이 좋습니다. 또한 팀 클라이언트 앱이 업데이트 될 때마다 규칙이 업데이트 되어야 하므로 해시 규칙을 사용 하지 않는 것이 좋습니다.

팀 데스크톱 실행 파일은 디지털 서명 되므로 게시자 조건은 디지털 서명 및 포함 된 버전 특성에 따라 앱 파일을 식별 합니다. 디지털 서명에는 앱 파일을 만든 회사에 대 한 정보가 포함 되어 있습니다 (게시자). 이진 리소스에서 가져온 버전 정보에는 해당 파일이 속한 제품의 이름과 응용 프로그램 파일의 버전 번호가 포함 됩니다.

### <a name="example-of-publisher-condition-rules"></a>Publisher 조건 규칙의 예

팀 클라이언트 앱 (모든 파일, 모든 버전)에 대해 DLL 규칙 & 실행 규칙에 다음을 추가 합니다.

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>관련 항목
[AppLocker 란?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [AppLocker 기술 참조](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)
