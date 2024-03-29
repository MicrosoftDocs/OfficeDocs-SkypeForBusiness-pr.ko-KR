---
title: Teams의 레거시 시스템에서 메시지 및 통화 수신 문제
ms.reviewer: ''
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 05/29/2020
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: 레거시 시스템에서 메시지 및 통화 수신과 관련된 문제 해결
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 56499af9534c3559cdfa3311a360caa60d06d3d7
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789523"
---
# <a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>레거시 시스템에서 메시지 및 통화 수신 문제

이전 버전의 Teams를 사용하거나 다른 애플리케이션에 로그인한 경우 사용자가 메시지 또는 전화를 받는 데 문제가 있을 수 있습니다.

## <a name="legacy-adu-setups"></a>레거시 ADU 설정

 **사용자가 도메인에 가입된 컴퓨터에 로그인하고 사용자 이름이 Teams 로그인 화면** 에 미리 채워지지 않도록 하려면 관리자가 다음 Windows 레지스트리를 설정하여 UPN(사용자 이름의 사전 채우기)를 해제할 수 있습니다.

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> ".local" 또는 ".corp"로 끝나는 사용자 이름에 대한 사용자 이름 미리 채우기를 건너뛰거나 무시하는 것이 기본적으로 설정되어 있으므로 이를 끄려고 레지스트리 키를 설정하지 않아도 됩니다.

자세한 내용은 [최신 인증을 사용하여 Microsoft Teams에 로그인](sign-in-teams.md) 을 참조하세요.

## <a name="skype-token-revocation"></a>Skype 토큰 해지

암호를 변경/재설정할 때 이전 클라이언트는 최대 1시간 동안 메시지와 호출을 받지 못합니다. 이 문제를 해결하려면 앱을 다시 시작하거나 최신 클라이언트로 이동합니다.


## <a name="related-topics"></a>관련 항목

[Teams 문제 해결](/MicrosoftTeams/troubleshoot/teams)