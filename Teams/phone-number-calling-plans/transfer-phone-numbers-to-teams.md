---
title: Microsoft 팀에 전화 번호 전송
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: ''
ms.openlocfilehash: b87684b6fbb73115540e20c72636200e61ca0e88
ms.sourcegitcommit: c4f13aa4947df606d38694a7e544b08be7ce20d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42370417"
---
# <a name="transfer-phone-numbers-to-microsoft-teams"></a>Microsoft 팀에 전화 번호 전송

[!INCLUDE [preview-feature](../includes/preview-feature.md)]

Microsoft 팀 관리 센터의 포팅 마법사를 사용 하 여 현재 서비스 공급자의 전화 번호를 팀으로 전환 합니다. 전화 번호를 팀으로 이식 하면 Microsoft가 서비스 공급자가 되며 해당 전화 번호로 청구 됩니다.

시작 하기 전에 [포트 순서](port-order-overview.md) 에 대 한 정보를 검토 하는 것이 좋습니다. 전화 접속 회의 브리지, 자동 전화 교환 또는 기타 서비스 번호, 무료 전화 번호, 팀에 게 전송 해야 하는 999 사용자 (구독자) 전화 번호 등의 서비스 번호가 있는 경우 [조직에서 전화 번호 관리](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 를 참조 하 여 올바른 양식을 다운로드 하 고 전자 메일을 보내 주세요.

  > [!NOTE]
  > 전화 번호를 미국 영업일 (공개 휴일 또는 주말에는 없음) 으로만 전송 하는 데 필요한 포트 주문을 처리 합니다.

## <a name="create-a-port-order-and-transfer-your-phone-numbers-to-teams"></a>포트 주문 만들기 및 전화 번호를 팀으로 전송

> [!NOTE]
> **현재이 마법사를 사용 하 여 영국 및 캐나다의 전화 번호를 얻을 수**있습니다. 다른 국가 및 지역에 대 한 전화 번호를 얻으려면 [포트 주문을 수동으로 제출할](manually-submit-port-order.md)수 있습니다. 포트 순서를 수동으로 제출 하는 데 필요한 양식을 가져오려면 [조직의 전화 번호 관리](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)에서 드롭다운 목록에서 국가 또는 지역을 선택 합니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성** > **전화 번호로**이동 합니다. **숫자**를 클릭 한 다음 **포트** 를 클릭 하 여 포팅 마법사를 시작 합니다.
2. **시작** 페이지의 정보를 검토 하 고 준비가 되 면 **다음**을 클릭 합니다.
3. **위치 및 번호 형식 선택** 페이지에서 다음을 지정 하 **고 다음을 클릭 합니다**.

    - **국가 또는 지역**: 번호를 받고 있는 국가 또는 지역입니다.
    - **전화 번호 형식**: 지역 또는 무료 전화 번호와 같은 번호 유형입니다.
    - 번호 **지정**대상: 번호가 배정 되는 항목 예를 들어 사용자, 회의 또는 음성 기능을 사용할 수 있습니다.

4. **계정 정보 추가** 페이지에서 다음을 완료 하 고 **다음**을 클릭 합니다.

    > [!IMPORTANT]
    > 이 페이지에 표시 되는 정보는 국가 또는 지역 및 번호 유형에 의해 결정 됩니다. 각 국가와 지역에는 포트 번호에 필요한 정보에 대 한 규정이 서로 다릅니다. 이 페이지에 표시 되는 내용은 여기에서 설명 하는 내용과 다를 수 있습니다.

    - **주문 정보**: 
        - **주문 이름**: 주문 이름
        - **알림 전자**메일: 주문 알림을 받을 주소를 전자 메일로 발송 합니다. 여러 개의 전자 메일 주소를 입력 하는 경우 세미콜론으로 구분 합니다.
        - **이전 날짜**: 현재 서비스 공급자가 발급 한 날짜입니다.
    - **전화 번호 정보**
        - **포트 유형**: 전체 포트를 수행 하 여 모든 번호를 전송 하는지 일부 번호를 전송 하는 것입니다.
    - **세부 정보를 요청 하는 사람**  
        - 전송을 요청 하는 사용자의 조직 이름 및 연락처 정보입니다.
    - **현재 공급자의 세부 정보**
        - **BTN (대금 청구 전화 번호)**: BTN에 + 기호를 추가 하 여 번호를 앞에 추가 해야 하는 E-f a f. 예를 들어 북미 번호의 경우 + 1XXXYYYZZZZ 형식을 사용 합니다.
        - 현재 서비스 공급자 이름, 계정 번호 및 서비스 주소를 비롯 한 기타 세부 정보
            
5. **번호 추가** 페이지에서 **파일 선택을**클릭 하 고 전송할 전화 번호가 포함 된 CSV 파일을 찾아 선택 하 고 **다음**을 클릭 합니다.  

    > [!NOTE]
    > CSV 파일에는 PhoneNumber 이라는 헤더가 있는 열이 하나만 있어야 합니다. 각 전화 번호는 별도의 행에 있어야 하 고 숫자만 입력 하거나 E. 형식으로 지정할 수 있습니다.

6. **주문 완료** 페이지에서 서명 된 승인 **문자 업로드** 를 클릭 하 여 서명 된 승인 된 편지 (LOA)의 스캔 한 복사본을 업로드 합니다.

    아직 LOA을 다운로드 하 여 서명 하지 않은 경우 다음을 수행 합니다.
    
    1. 국가 또는 지역에 대 한 LOA를 다운로드 하려면 **서식 파일 다운로드** 를 클릭 합니다. 
    2. LOA을 인쇄 합니다.
    3. 계정을 변경할 수 있는 권한이 있는 사람이 서명한 LOA을 사용 합니다.
    4. 서명 된 LOA를 스캔 한 다음 **서명 된 승인 문자 업로드** 를 클릭 하 여 업로드 합니다.

    > [!NOTE]
    > LOA를 업로드 한 후 주문을 제출 합니다. LOA를 업로드 하는 것 만으로는 충분 하지 않습니다. 또한 처리 되는 주문을 제출 해야 합니다.

7. 주문 내역을 검토 한 다음 **제출을**클릭 합니다.


## <a name="what-happens-next"></a>그 다음은 어떻게 되나요?

포트 주문을 받으면 요청을 확인 하는 전자 메일을 받게 됩니다. 매일 요청이 확인 되 고 업데이트 되었으며, 전자 메일의 진행률과 상태에 대 한 알림을 받게 됩니다. 반송파 손실에 의해 포트 요청이 거부 되는 경우 [PSTN 서비스 데스크](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)에 문의 하세요.

포트 순서의 상태를 보려면 Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 > **음성** > **포트 주문**으로 이동한 다음 **주문 기록을**클릭 합니다. 각 포트 주문 상태가 **상태** 열에 나열 됩니다. 자세한 내용은 [포트 주문의 상태](port-order-status.md) 를 참조 하세요.

## <a name="related-topics"></a>관련 주제

- [포트 순서](port-order-overview.md)
- [통화 요금제에 사용 되는 다른 종류의 전화 번호](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [조직의 전화 번호 관리](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [긴급 통화 사용 약관](../emergency-calling-terms-and-conditions.md)
- [비상 전화 고 지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
