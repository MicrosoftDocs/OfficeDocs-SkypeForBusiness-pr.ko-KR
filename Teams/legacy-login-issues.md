---
title: 팀의 레거시 시스템에서 메시지 및 통화를 수신 하는 문제
ms.reviewer: ''
author: cichur
ms.author: v-cichur
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
description: 이전 시스템에서 메시지 수신 및 통화와 관련 된 문제 해결
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 52038470e81b825391e4176c07af7a30f51356df
ms.sourcegitcommit: ef3cd762e799df43bdcde03363c501d7ca9bb6b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2020
ms.locfileid: "44489167"
---
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>레거시 시스템에서 메시지 및 통화 수신 문제
==============================================================

사용자가 이전 버전의 팀을 사용 중이거나 다른 응용 프로그램에 로그인 한 경우 메시지 또는 통화를 수신 하는 동안 문제가 발생할 수 있습니다.

## <a name="legacy-adu-setups"></a>레거시 ADU

 **사용자가 도메인에 가입된 컴퓨터에 로그인하고 사용자 이름이 Teams 로그인 화면**에 미리 채워지지 않도록 하려면 관리자가 다음 Windows 레지스트리를 설정하여 UPN(사용자 이름의 사전 채우기)를 해제할 수 있습니다.

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> ".local" 또는 ".corp"로 끝나는 사용자 이름에 대한 사용자 이름 미리 채우기를 건너뛰거나 무시하는 것이 기본적으로 설정되어 있으므로 이를 끄려고 레지스트리 키를 설정하지 않아도 됩니다.

자세한 내용은 [최신 인증을 사용 하 여 Microsoft 팀에 로그인을](sign-in-teams.md) 참조 하세요.

## <a name="skype-token-revocation"></a>Skype 토큰 해지

비밀 번호를 변경/재설정 하는 경우 구형 클라이언트는 최대 1 시간 동안 메시지와 통화를 받을 수 없습니다. 이 문제를 해결 하려면 앱을 다시 시작 하거나 최신 클라이언트로 이동 하세요.
