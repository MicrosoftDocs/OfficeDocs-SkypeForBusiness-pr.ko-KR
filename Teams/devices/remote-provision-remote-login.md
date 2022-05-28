---
title: Teams Android 디바이스에 대한 원격 프로비저닝 및 로그인
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Teams Android 디바이스에 대한 원격 프로비전 및 로그인 방법 알아보기
ms.openlocfilehash: 5a746e3255ce8af9bcf59f8dfcae12854b222a1f
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761290"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a>Teams Android 디바이스에 대한 원격 프로비저닝 및 로그인

IT 관리자는 원격으로 프로비전하고 Teams Android 디바이스에 로그인할 수 있습니다. 디바이스를 원격으로 프로비전하려면 관리자가 프로비전 중인 디바이스의 MAC ID를 업로드하고 확인 코드를 만들어야 합니다. 전체 프로세스는 Teams 관리 센터에서 원격으로 완료할 수 있습니다.

## <a name="review-the-supported-devices"></a>지원되는 디바이스 검토

다음 목록에서는 Android 디바이스 펌웨어 요구 사항을 보여 줍니다.

|디바이스 범주|디바이스 모델|펌웨어 버전|
|---|---|---|
|휴대폰 Teams|Yealink T55/T56/T58|58.15.0.124|
|휴대폰 Teams|Yealink VP59|91.15.0.58|
|휴대폰 Teams|Yealink CP960|73.15.0.117|
|휴대폰 Teams|Yealink MP56/MP54/MP58|122.15.0.36|
|휴대폰 Teams|크레스트론 UC-2|1.0.3.52|
|휴대폰 Teams|Poly Trio C60|7.0.2.1071|
|휴대폰 Teams|CCX400/CCX500/CCX600 |7.0.2.1072|
|휴대폰 Teams|오디오 코드 C448HD/C450HD/C470HD|1.10.120|
|Teams 패널|크레스트론 770/1070|1.004.0115|
|Android Teams 룸|Logitech Rally Bar Mini|1.2.982|
|Android Teams 룸|Logitech Rally Bar|1.2.982|
|Android Teams 룸|AudioCodes RXV80|1.13.361|
|Android Teams 룸|EPOS EXPAND Vision 3T|1.2.2.21182.10|
|Android Teams 룸|Yealink MeetingBar A30|133.15.0.60|
|Android Teams 룸|Yealink MeetingBar A20|133.15.0.60|
|Android Teams 룸|Yealink CTP18 터치 콘솔|137.15.0.37|
|Android Teams 룸|Poly Studio X30|3.5.0.344025|
|Android Teams 룸|Poly Studio X50|3.5.0.344025|
|Android Teams 룸|Poly TC8 터치 콘솔 |3.5.0.210489|
|Android Teams 룸|Yealink VC210|118.15.0.54|

## <a name="add-a-device-mac-address"></a>디바이스 MAC 주소 추가

다음 단계를 완료하여 새 디바이스를 프로비전합니다.

1. Teams 관리 센터에 로그인합니다.
2. **Teams 디바이스** 를 확장합니다.
3. **작업** 탭에서 **새 디바이스 프로비저닝** 을 선택합니다.

**새 디바이스 프로비전** 창에서 MAC 주소를 수동으로 추가하거나 파일을 업로드할 수 있습니다.

### <a name="manually-add-a-device-mac-address"></a>수동으로 디바이스 MAC 주소 추가

1. **활성화 대기** 중 탭에서 **MAC ID 추가** 를 선택합니다.

   ![수동으로 디바이스 mac 주소를 추가합니다.](../media/remote-provision-6-new.png)

1. MAC ID를 입력합니다.
1. 기술자가 디바이스를 설치할 위치를 식별하는 데 도움이 되는 위치를 입력합니다.
1. 완료되면 **적용** 을 선택합니다.

### <a name="upload-a-file-to-add-a-device-mac-address"></a>디바이스 MAC 주소를 추가하는 파일 업로드

1. **활성화 대기** 중 탭에서 **업로드 MAC ID를** 선택합니다.
2. 파일 템플릿을 다운로드합니다.
3. MAC ID 및 위치를 입력한 다음 파일을 저장합니다.
4. **파일을 선택한** 다음 **, 업로드** 선택합니다.

## <a name="generate-a-verification-code"></a>확인 코드 생성

디바이스에 대한 확인 코드가 필요합니다. 확인 코드는 대량 또는 디바이스 수준에서 생성되며 24시간 동안 유효합니다.

1. **활성화 대기** 중 탭에서 기존 MAC ID를 선택합니다.
   MAC 주소에 대한 암호가 만들어지고 **확인 코드** 열에 표시됩니다.

2. 현장 기술자에게 MAC ID 및 확인 코드 목록을 제공합니다. 파일에서 직접 세부 정보를 내보내고 실제 설치 작업을 수행하는 기술자와 파일을 공유할 수 있습니다.

## <a name="provision-the-device"></a>디바이스 프로비전

디바이스가 켜지고 네트워크에 연결되면 기술자가 디바이스를 프로비전합니다. 이러한 단계는 Teams 디바이스에서 완료됩니다.

1. 기술자는 **설정** **디바이스 프로비저닝** 을 선택합니다.  

   ![작업 탭에서 새 디바이스 옵션을 프로비전합니다.](../media/provision-device1.png)
  
2. 기술자는 제공된 입력 필드에 디바이스별 확인 코드를 입력합니다.

   ![새 디바이스 확인을 프로비전합니다.](../media/provision-device-verification1.png)

   디바이스가 성공적으로 프로비전되면 로그인 페이지에 테넌트 이름이 표시됩니다.

   ![로그인 페이지의 테넌트 이름입니다.](../media/provision-code.png)

## <a name="first-time-remote-sign-in"></a>처음 원격 로그인

프로비전된 디바이스가 **로그인 대기 탭에** 나타납니다. 개별 디바이스를 선택하여 원격 로그인 프로세스를 시작합니다.

1. **로그인 대기** 탭에서 디바이스를 선택합니다.

   ![로그인할 준비가 된 디바이스 목록이 있는 창입니다.](../media/remote-device1.png)

2. **사용자 로그인** 의 지침에 따라 **닫기를** 선택합니다.

   ![개별 디바이스에 대한 사용자 로그인 창입니다.](../media/sign-in-user.png)

## <a name="related-articles"></a>관련 기사

- [Teams에서 디바이스 관리](device-management.md)
- [원격 로그인 및 로그아웃](remote-sign-in-and-sign-out.md)
- [원격으로 Teams 디바이스 업데이트](remote-update.md)
