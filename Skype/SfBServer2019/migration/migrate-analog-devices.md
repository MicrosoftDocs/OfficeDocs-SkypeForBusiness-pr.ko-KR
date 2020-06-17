---
title: 아날로그 장치 마이그레이션
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 비즈니스용 Skype 서버는 아날로그 장치에 대 한 지원을 제공 합니다. 특히 지원되는 아날로그 장치가 아날로그 오디오 전화와 아날로그 팩스입니다. 비즈니스용 Skype 서버 환경에서 아날로그 장치 사용을 지원 하도록 자격 있는 게이트웨이를 구성할 수 있습니다. 비즈니스용 Skype 서버 2019로 마이그레이션한 후에는 아날로그 장치와 연결 된 대화 상대 개체도 마이그레이션해야 합니다. 비즈니스용 Skype 서버 관리 셸을 사용 하 여 먼저 레거시 아날로그 장치와 연결 된 모든 대화 상대 개체를 검색 한 후 해당 개체를 비즈니스용 Skype 서버 2019 풀로 이동 합니다.
ms.openlocfilehash: 7b90a52486725c2cf30856dc643660d569d698e2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752830"
---
# <a name="migrate-analog-devices"></a>아날로그 장치 마이그레이션

비즈니스용 Skype 서버는 아날로그 장치에 대 한 지원을 제공 합니다. 특히 지원되는 아날로그 장치가 아날로그 오디오 전화와 아날로그 팩스입니다. 비즈니스용 Skype 서버 환경에서 아날로그 장치 사용을 지원 하도록 자격 있는 게이트웨이를 구성할 수 있습니다. 비즈니스용 Skype 서버 2019로 마이그레이션한 후에는 아날로그 장치와 연결 된 대화 상대 개체도 마이그레이션해야 합니다. 비즈니스용 Skype 서버 관리 셸을 사용 하 여 먼저 레거시 아날로그 장치와 연결 된 모든 대화 상대 개체를 검색 한 후 해당 개체를 비즈니스용 Skype 서버 2019 풀로 이동 합니다.

### <a name="to-migrate-analog-devices"></a>아날로그 장치를 마이그레이션하려면

1. 비즈니스용 Skype 서버 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft 비즈니스용 skype 서버 2019**을 차례로 클릭 한 다음 **비즈니스용 skype 서버 관리 셸을**클릭 합니다.

2. 명령줄에 다음을 입력합니다.

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. 모든 대화 상대 개체가 비즈니스용 Skype 서버 2019 풀로 이동 되었는지 확인 합니다. 명령줄에 다음을 입력합니다.

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. 모든 대화 상대 개체가 이제 비즈니스용 Skype 서버 2019 풀과 연결 되어 있는지 확인 합니다.


