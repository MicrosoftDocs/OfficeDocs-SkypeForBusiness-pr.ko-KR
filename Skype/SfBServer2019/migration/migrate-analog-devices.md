---
title: 아날로그 장치 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 비즈니스용 Skype Server는 아날로그 장치에 대 한 지원을 제공 합니다. 특히 지원 되는 아날로그 장치는 아날로그 오디오 전화와 아날로그 팩스 컴퓨터입니다. 비즈니스용 Skype 서버 환경에서 아날로그 장치 사용을 지원 하도록 정식 게이트웨이를 구성할 수 있습니다. 비즈니스용 Skype 서버 2019으로 마이그레이션한 후에는 아날로그 장치와 관련 된 연락처 개체도 마이그레이션해야 합니다. 비즈니스용 Skype Server Management Shell을 사용 하 여 먼저 레거시 아날로그 장치와 관련 된 모든 contact 개체를 검색 한 다음 해당 개체를 비즈니스용 Skype 서버 2019 풀로 이동 합니다.
ms.openlocfilehash: 486c49c0ace00b798520ebae939c0c2070a99783
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238736"
---
# <a name="migrate-analog-devices"></a>아날로그 장치 마이그레이션

비즈니스용 Skype Server는 아날로그 장치에 대 한 지원을 제공 합니다. 특히 지원 되는 아날로그 장치는 아날로그 오디오 전화와 아날로그 팩스 컴퓨터입니다. 비즈니스용 Skype 서버 환경에서 아날로그 장치 사용을 지원 하도록 정식 게이트웨이를 구성할 수 있습니다. 비즈니스용 Skype 서버 2019으로 마이그레이션한 후에는 아날로그 장치와 관련 된 연락처 개체도 마이그레이션해야 합니다. 비즈니스용 Skype Server Management Shell을 사용 하 여 먼저 레거시 아날로그 장치와 관련 된 모든 contact 개체를 검색 한 다음 해당 개체를 비즈니스용 Skype 서버 2019 풀로 이동 합니다.

### <a name="to-migrate-analog-devices"></a>아날로그 장치 마이그레이션

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **Microsoft 비즈니스용 skype 서버 2019**을 차례로 클릭 한 다음 비즈니스용 **skype server management shell**을 클릭 합니다.

2. 명령줄에 다음을 입력 합니다.

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. 모든 연락처 개체를 비즈니스용 Skype 서버 2019 풀로 이동 했는지 확인 합니다. 명령줄에 다음을 입력 합니다.

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. 모든 contact 개체가 비즈니스용 Skype 서버 2019 풀에 연결 되어 있는지 확인 합니다.


