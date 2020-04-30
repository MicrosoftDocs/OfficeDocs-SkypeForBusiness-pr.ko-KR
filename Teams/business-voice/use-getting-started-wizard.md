---
title: 시작 마법사를 사용하여 Business Voice 설정하기
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9a22c741898b48c3d71970699f09c00bb638205f
ms.sourcegitcommit: 3ef5c913318fdeeaa8c55caab07c2f8224eae2b0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43898133"
---
# <a name="use-the-getting-started-wizard-to-set-up-business-voice"></a>시작 마법사를 사용하여 Business Voice 설정하기

> [!IMPORTANT]
> 이 문서의 정보는 통화 플랜이 **포함된** Business Voice에만 적용됩니다. 통화 플랜이 포함된 Business Voice는 선택된 국가 및 지역에서만 사용할 수 있습니다. 이 문서를 읽기 전에 [Business Voice의 국가 및 지역 가용성](country-region-availability.md)을 확인하여 해당 국가 또는 지역에서 통화 플랜이 포함된 Business Voice를 지원하는지 확인하세요.
>
> 테넌트가 통화 플랜을 포함한 Business Voice를 지원하지 않는 국가 또는 지역에 있는 경우 [Microsoft 리셀러 또는 파트너에게 도움 받기](reseller-partner-support.md)를 확인하세요.

Microsoft 365 Business Voice용 시작 마법사를 사용하면 Microsoft Teams에서 전화를 걸고 받도록 빠르게 설정할 수 있습니다. 갓 시작한 중소기업에서는 마법사를 사용해 몇 분 안에 전화번호, 통화 메뉴, 인사말 등을 사용할 수 있습니다. 전화 통신 솔루션을 구축한 대기업의 경우 모든 사용자를 위해 Business Service를 설정하기 전에 마법사를 통해 파일럿을 설정하여 일부 사용자가 먼저 사용해 볼 수 있습니다. 두 경우 모두 마법사가 완료되면 Business Voice 사용을 시작할 수 있습니다.

마법사를 시작하기 전에 이 문서를 읽는 것이 좋습니다. 마법사를 실행할 준비가 되면 [Microsoft 365 Business Voice 시작](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/featureexplorer/apps/SmbVoice) 페이지에서 **시작**을 선택합니다. 구독을 만들 때 사용한 계정 또는 전역 관리자인 다른 계정을 사용하여 로그인합니다.

> [!IMPORTANT]
> Microsoft Teams와 Business Voice는 사용자의 사서함이 Microsoft 365에 있는 경우에만 사용할 수 있습니다.  온-프레미스 Exchange 서버의 사서함은 지원하지 않습니다.

<!-- After you've finished the wizard, you may want to check out the following articles:

* [Things to try with Business Voice](things-to-try.md)
* [Business Voice design customization](customize-business-voice.md)-->

지금 바로 사용자 정의할 것이 없는 경우, 설정이 완료되었습니다! Business Voice를 바로 사용할 수 있습니다.

## <a name="emergency-services-location"></a>긴급 서비스 위치

<table>
    <tr>
        <td>긴급 주소를 변경하려면 <b>편집</b>을 클릭하고 새 주소를 입력합니다. 입력하는 주소는 긴급 대응 서비스에 적절하며 형식이 올바른지 확인을 거칩니다. 그런 다음 이 주소는 다음 단계에서 번호를 할당한 모든 사용자에게 할당됩니다. 둘 이상의 위치에 직원이 있는 경우 시작 마법사를 준비한 후 더 많은 긴급 주소를 추가하고 할당하려면 <a href="./customize-business-voice.md">Business Voice 디자인 사용자 지정</a>을 참조하세요.</td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400"></td></tr>
</table>

자세한 내용은 [긴급 위치, 주소 및 통화 라우팅이 무엇인가요?](../what-are-emergency-locations-addresses-and-call-routing.md)를 참조하세요.

## <a name="company-phone-number"></a>회사 전화번호

<table>
    <tr>
        <td>새 현지 전화번호 외에도 무료 전화 번호를 구입하거나 기존 번호를 Microsoft 365로 이식할 수 있습니다. 무료 전화 번호를 설정하려면 커뮤니케이션 크레딧을 구입해야 합니다. 하나 이상의 번호를 Microsoft 365로 이식하려면 마법사가 완료된 후 <a href="https://admin.teams.microsoft.com">팀 관리 센터</a>로 이동합니다.
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> 기존 전화번호를 Microsoft 365로 이식하도록 선택해도 마법사에 임시 전화번호가 계속 표시됩니다. 예상된 동작입니다. 마법사와 이식 절차를 완료하면 임시 전화 번호가 기존 번호로 바뀝니다.

## <a name="user-licenses"></a>사용자 라이선스

<table>
    <tr>
        <td>사용자 라이선스를 할당하려면 Teams 외부와 통화(예: 공급업체에 전화)가 필요한 조직의 일원을 선택합니다. 사용 가능한 만큼의 Business Voices 라이선스만 할당할 수 있습니다. 라이선스가 더 필요한 경우 마법사가 완료된 후 추가 라이선스를 구입할 수 있습니다.
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-get-numbers.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> 마법사가 완료된 후 기존 전화 번호를 Microsoft 365로 이식할 수 있습니다. 이식 절차를 완료하면 마법사가 제공한 임시 전화번호가 이식된 전화번호로 바뀝니다.

## <a name="incoming-call-greeting"></a>수신 전화 인사말

<table>
    <tr>
        <td>5MB 이하의 음성 파일(MP3 또는 WAV)을 업로드해 전화 인사말로 사용할 수 있습니다. 또는 인사말을 텍스트로 입력하면 Microsoft 365가 TTS 기능을 사용해 발신자에게 읽어줍니다. 인사말은 발신자가 회사 전화번호로 전화를 걸었을 때 처음 듣게 되는 소리입니다. TTS(텍스트 음성 변환)의 경우 발음을 정확히 하기 위해 표음식 철자를 사용해야 할 수도 있습니다.
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-greeting.png" width="400">
        </td>
    </tr>
</table>

## <a name="call-menu-and-forwarding"></a>통화 메뉴 및 착신 전환

<table>
    <tr>
        <td>모든 통화를 특정 사용자에게 착신 전환하거나, 발신자가 옵션을 선택할 수 있도록 메뉴를 설정할 수 있습니다. 통화 메뉴를 만드는 경우 발신자가 음성 또는 전화 키패드의 번호를 눌러 선택할 수 있는 옵션을 지정합니다. 각 메뉴 옵션은 특정 사용자에게 착신 전활할 수 있습니다.<br><br>
        발신자에게 지침을 제공하는 5MB 이하의 음성 파일(MP3 또는 WAV)을 업로드하거나 지침을 텍스트로 입력할 수 있습니다. Microsoft 365는 텍스트 음성 변환을 사용하여 발신자에게 지침을 읽어줍니다. 발음을 정확히 하기 위해 발음에 맞는 철자를 입력해야 할 수 있습니다.
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-call-forwarding-rules.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> 시작 마법사를 사용하면 빠르게 실행할 수 있는 간단한 통화 메뉴를 설정할 수 있습니다. 통화 메뉴를 설정하려는 번호가 여러 개인 경우나 좀 더 복잡한 통화 메뉴(자동 전화 교환)를 설정하려는 경우는 마법사를 완료한 후 [클라우드 자동 전화 교환 설정](set-up-auto-attendants.md)을 참조하십시오.

<table>
    <tr>
        <td> <p>시작 마법사는 입력한 정보를 사용하여 Business Voice를 설정합니다. <b>개요</b> 페이지에서 사용자에게 할당되는 전화번호를 확인하고, 통화 메뉴를 살펴보고, 인사말을 들을 수 있습니다.</p>
             <p>설치하는 데 몇 분 정도 걸립니다. <b>완료</b>를 선택하면 백그라운드에서 Business Voice가 계속 설정됩니다. 또는 설치가 완료될 때까지 기다립니다. 설정이 완료되면 <a href="https://admin.teams.microsoft.com" target="_blank">Teams 관리 센터</a>에서 <b>음성</b>으로 이동하여 더 많은 Business Voice 기능을 설정하세요.</p>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-finish-page.png" width="400">
        </td>
    </tr>
</table>
