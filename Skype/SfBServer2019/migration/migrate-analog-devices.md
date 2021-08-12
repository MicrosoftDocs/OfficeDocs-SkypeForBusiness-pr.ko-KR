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
description: 비즈니스용 Skype 서버 아날로그 장치를 지원합니다. 특히 지원되는 아날로그 장치가 아날로그 오디오 전화와 아날로그 팩스입니다. 사용자 환경의 아날로그 장치 사용을 지원하도록 적격 게이트웨이를 구성할 비즈니스용 Skype 서버 있습니다. 2019년 비즈니스용 Skype 서버 마이그레이션한 후 아날로그 장치와 연결된 연락처 개체도 마이그레이션해야 합니다. 비즈니스용 Skype 서버 관리 셸을 사용하여 먼저 레거시 아날로그 장치와 연결된 모든 연락처 개체를 검색한 다음 해당 개체를 비즈니스용 Skype 서버 2019 풀로 이동할 수 있습니다.
ms.openlocfilehash: 464531fcffbe251d6a0868e86b1b9edccc898fdeeb0963ed0f10c2b653dfe93b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337268"
---
# <a name="migrate-analog-devices"></a>아날로그 장치 마이그레이션

비즈니스용 Skype 서버 아날로그 장치를 지원합니다. 특히 지원되는 아날로그 장치가 아날로그 오디오 전화와 아날로그 팩스입니다. 사용자 환경의 아날로그 장치 사용을 지원하도록 적격 게이트웨이를 구성할 비즈니스용 Skype 서버 있습니다. 2019년 비즈니스용 Skype 서버 마이그레이션한 후 아날로그 장치와 연결된 연락처 개체도 마이그레이션해야 합니다. 비즈니스용 Skype 서버 관리 셸을 사용하여 먼저 레거시 아날로그 장치와 연결된 모든 연락처 개체를 검색한 다음 해당 개체를 비즈니스용 Skype 서버 2019 풀로 이동할 수 있습니다.

### <a name="to-migrate-analog-devices"></a>아날로그 장치를 마이그레이션하려면

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, Microsoft 비즈니스용 Skype 서버 **2019를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**

2. 명령줄에 다음을 입력합니다.

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. 모든 연락처 개체가 2019 풀로 비즈니스용 Skype 서버 확인 명령줄에 다음을 입력합니다.

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. 이제 모든 연락처 개체가 2019 풀과 비즈니스용 Skype 서버 있는지 확인해야 합니다.


