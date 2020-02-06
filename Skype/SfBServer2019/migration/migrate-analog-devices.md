---
title: 아날로그 장치 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 비즈니스용 Skype Server는 아날로그 장치에 대 한 지원을 제공 합니다. 특히 지원 되는 아날로그 장치는 아날로그 오디오 전화와 아날로그 팩스 컴퓨터입니다. 비즈니스용 Skype 서버 환경에서 아날로그 장치 사용을 지원 하도록 정식 게이트웨이를 구성할 수 있습니다. 비즈니스용 Skype 서버 2019으로 마이그레이션한 후에는 아날로그 장치와 관련 된 연락처 개체도 마이그레이션해야 합니다. 비즈니스용 Skype Server Management Shell을 사용 하 여 먼저 레거시 아날로그 장치와 관련 된 모든 contact 개체를 검색 한 다음 해당 개체를 비즈니스용 Skype 서버 2019 풀로 이동 합니다.
ms.openlocfilehash: b3b3cc1ebafa468a43043b202a01957c1cc06e87
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813596"
---
# <a name="migrate-analog-devices"></a>아날로그 장치 마이그레이션

비즈니스용 Skype Server는 아날로그 장치에 대 한 지원을 제공 합니다. 특히 지원 되는 아날로그 장치는 아날로그 오디오 전화와 아날로그 팩스 컴퓨터입니다. 비즈니스용 Skype 서버 환경에서 아날로그 장치 사용을 지원 하도록 정식 게이트웨이를 구성할 수 있습니다. 비즈니스용 Skype 서버 2019으로 마이그레이션한 후에는 아날로그 장치와 관련 된 연락처 개체도 마이그레이션해야 합니다. 비즈니스용 Skype Server Management Shell을 사용 하 여 먼저 레거시 아날로그 장치와 관련 된 모든 contact 개체를 검색 한 다음 해당 개체를 비즈니스용 Skype 서버 2019 풀로 이동 합니다.

### <a name="to-migrate-analog-devices"></a>아날로그 장치 마이그레이션

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **Microsoft 비즈니스용 skype 서버 2019**을 차례로 클릭 한 다음 비즈니스용 **skype server management shell**을 클릭 합니다.

2. 명령줄에 다음을 입력 합니다.

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. 모든 연락처 개체를 비즈니스용 Skype 서버 2019 풀로 이동 했는지 확인 합니다. 명령줄에 다음을 입력 합니다.

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. 모든 contact 개체가 비즈니스용 Skype 서버 2019 풀에 연결 되어 있는지 확인 합니다.


