---
title: 사용자의 전화 번호 검색
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: davlick, roykuntz, jastark
ms.topic: article
ms.assetid: cc22c49a-c644-4151-a2fc-a1474148f8ba
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 국가 또는 지역 및 도시별로 사용자에게 할당할 수 있는 전화 번호를 검색하고 필요한 번호의 수량을 지정하는 방법을 알아보세요.
ms.openlocfilehash: 43aef76a16a8505e34407b15068a546dd2894343
ms.sourcegitcommit: d87991ed2d3e4d70edb048378763a17ff689b710
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2022
ms.locfileid: "66682507"
---
# <a name="search-for-telephone-numbers-for-users"></a>사용자의 전화 번호 검색

조직에서 Microsoft 제공 전화 번호를 사용하여 전화를 걸고 받을 수 있도록 설정하는 경우 먼저 **Microsoft Teams 관리 센터를** 사용하고 사용자에게 할당할 전화 번호를 획득해야 합니다. 사용자에게 할당하는 전화 번호는 조직에서 이전에 획득한 전화 번호입니다. 사용자의 속성을 편집하고 **[할당**]을 클릭하면 숫자가 드롭다운 목록에 나열됩니다.
  
Microsoft에서 제공한 전화 번호를 사용자에게 할당하려면 먼저 **새 번호 가져오기** 페이지를 사용하여 사용 가능한 전화 번호를 검색해야 합니다. **국가(시장)**, **번호 유형** 및 위치를 기준으로 검색할 수 **있습니다**. 그런 다음 해당 국가에서 숫자를 제공하는 연산자 목록이 표시됩니다.

운영자로 Microsoft를 선택하는 경우 사용자에게 필요한 전화 번호의 수량을 입력하여 Teams 관리 센터에서 번호를 가져올 수 있습니다. 페이지에서는 계속 획득할 수 있는 수량에 따라 수량을 자동으로 제한합니다. 연산자 연결 연산자를 선택하면 선택한 연산자의 방문 페이지로 이동하여 번호 순서를 완료합니다.

전화 번호를 획득하고 관리하는 방법은 PSTN 연결 옵션(Microsoft 통화 플랜, 운영자 연결 또는 직접 라우팅)에 따라 다릅니다.

이 문서는 [Microsoft 통화 플랜](#search-for-telephone-numbers-for-microsoft-calling-plans) 및 [운영자 연결](#search-for-telephone-numbers-for-operator-connect)에 적용됩니다. 모든 옵션에 대한 자세한 내용은 [조직의 전화 번호 관리를 참조하세요](/microsoftteams/manage-phone-numbers-landing-page).

## <a name="search-for-telephone-numbers-for-microsoft-calling-plans"></a>Microsoft 통화 플랜에 대한 전화 번호 검색

사용자의 전화 번호를 검색하려면 다음을 수행합니다.
  
1. **Microsoft Teams 관리 센터로** 이동합니다.

2. 왼쪽 탐색 창에서 **음성** > **전화 번호 새 번호** > **가져오기를** 선택합니다.
  
    > [!IMPORTANT]
    > Teams 관리 센터의 왼쪽 탐색 영역에서 **음성** 옵션을 보려면 먼저 **하나 이상의 Enterprise E5 또는 E3 라이선스**, **하나의 전화 시스템** 추가 기능 라이선스 또는 하나의 **오디오 회의** 추가 기능 라이선스를 구입해야 합니다.  

3. **위치 및 수량 선택** 페이지의 **국가(시장)** 드롭다운 목록에서 위치를 선택합니다.

4. **숫자 유형** 드롭다운 목록에서 **사용자를** 선택합니다.

5. 선택한 국가(시장)에 따라 이제 필요한 전화 번호를 찾는 데 사용할 수 있는 다양한 옵션이 제공됩니다.  

6. **수량** 에서 조직에 대해 원하는 전화 번호 수를 입력하고 **다음** 을 클릭합니다. 전화 번호를 선택하는 데 10분이 걸립니다. 10분 이상 걸리는 경우 전화 번호 풀에 번호가 반환됩니다.

    > [!NOTE]
    > **수량** 옆에 나열된 사용 가능한 전화 번호 수(라이선스 수 기준)를 볼 수 있습니다.
  
7. **번호 가져오기** 페이지에서 원하는 전화 번호를 선택하고 **번호 가져오기** 를 클릭한 다음 **다음** 을 클릭합니다.

    > [!IMPORTANT]
    > Microsoft 라이선스보다 더 많은 전화 번호를 얻을 수 있습니다. 획득할 수 있는 전화 번호 수를 확인하려면 Microsoft 통화 플랜 라이선스 수를 사용하고, 라이선스 수의 10%를 추가한 다음, 10을 추가한 다음, 이미 획득한 전화 번호를 제거합니다. 예를 들어 Microsoft **국내 통화 플랜** 및/또는 **국제 통화 플랜** 라이선스가 100개인 경우 해당 100명의 사용자에 대한 전화 번호를 아직 취득하지 않은 경우 120개의 전화 번호를 예약할 수 있습니다. 자세한 내용은 [얼마나 많은 전화 번호를 받을 수 있나요?](./how-many-phone-numbers-can-you-get.md)를 참조하세요.

8. **확인** 페이지에서 선택 항목을 확인한 다음 **주문 배치** 를 클릭합니다.

9. **전화 번호** 페이지로 돌아가면 할당할 전화 번호 또는 번호를 선택한 다음 **편집** 을 클릭하여 사용자에게 할당합니다.

## <a name="search-for-telephone-numbers-for-operator-connect"></a>운영자 연결에 대한 전화 번호 검색

1. **Microsoft Teams 관리 센터로** 이동합니다.

2. 왼쪽 탐색 창에서 **음성** > **전화 번호 새 번호** > **가져오기를** 선택합니다.
  
    > [!IMPORTANT]
    > Teams 관리 센터의 왼쪽 탐색 영역에서 **음성** 옵션을 보려면 먼저 **하나 이상의 Enterprise E5 또는 E3 라이선스**, **하나의 전화 시스템** 추가 기능 라이선스 또는 하나의 **오디오 회의** 추가 기능 라이선스를 구입해야 합니다.  

3. **위치 및 수량 선택** 페이지의 **국가(시장)** 드롭다운 목록에서 위치를 선택합니다.

4. **숫자 유형** 드롭다운 목록에서 **사용자를** 선택합니다.

5. 선택한 국가(시장)에 따라 이제 필요한 전화 번호를 찾는 데 사용할 수 있는 다양한 옵션이 제공됩니다. 내 연산자 **표시** 를 선택하여 추가한 연산자만 표시하도록 필터링할 수 있습니다.

6. 운영자에게 이미 동의한 경우 주문 프로세스를 완료하기 위해 운영자의 방문 페이지로 이동됩니다.

7. 운영자에게 동의를 제공하지 않은 경우 Teams 관리 센터의 선택한 운영자 페이지에서 운영자를 사용하도록 설정하라는 지시가 표시됩니다. 자세한 내용은 [연산자 사용을](operator-connect-configure.md#enable-an-operator) 참조하세요.

8. 주문이 완료되면 운영자가 테넌트에 전화 번호를 업로드하고 사용자에게 할당할 수 있습니다.  

## <a name="related-topics"></a>관련 항목

[조직의 전화 번호 관리](manage-phone-numbers-landing-page.md)

[긴급 통화 사용 약관](./emergency-calling-terms-and-conditions.md)

[긴급 통화 고지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
