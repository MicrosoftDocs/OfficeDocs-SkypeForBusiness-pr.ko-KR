---
title: '질문과 대답: Skype 연결용 Lync Server 프로 비전'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Frequently Asked Questions: Provisioning Lync Server for Skype connectivity'
ms:assetid: 4d1b2bfc-780b-4b8c-afd5-11c2e59203b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440172(v=OCS.15)
ms:contentKeyID: 57793362
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 718dda9966b79ca75f64df115dc9a6ba30d15619
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="frequently-asked-questions-provisioning-lync-server-2013-for-skype-connectivity"></a>질문과 대답: Skype 연결용 Lync Server 2013 프로 비전

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2019-03-22_

4 월 2019 부터는 pic.lync.com 웹 사이트를 통해 Skype 페더레이션을 프로 비전 한 고객에 대 한 연락처 정보의 수집 및 보존이 중지 됩니다. 이렇게 변경 하면 pic.lync.com 프로 비전 시스템이 Microsoft 개인 정보 취급 방침을 준수 하 게 됩니다. 
 
이 변경이 라이브 되 면 더 이상 보류 중인 프로 비전 변경 내용에 대 한 전자 메일 업데이트를 제공할 수 없게 됩니다. PIC 프로 비전 변경 내용은 일반적으로 입력 후 24-48 시간 이내에 완료 됩니다. 프로 비전 요청을 제출한 후에도 계속 해 서 Skype 페더레이션 48 문제가 발생 하는 경우에는 Microsoft 기술 지원 서비스에 문의 하 여 추가 조사를 진행 하세요.

> [!IMPORTANT]
> 이 변경의 일환으로 이전에 입력 한 모든 연락처 정보는 4 월 말까지 시스템에서 제거 됩니다 (2019).


**Q: Microsoft Lync와 Skype 간에 지원 되는 기능은 무엇입니까?**

**A:** Microsoft 가족의 Skype를 사용 하는 경우, Skype를 사용 하는 수백 명에 게 통합 커뮤니케이션 시나리오를 확장 하기 위해 새로운 가능성이 향상 되었습니다. 이 조합을 사용 하면 Lync 고객이 공급자, 고객 및 파트너와 연결 하 고 공동 작업을 수행 하 여 Lync 및 Skype의 다양성을 활용할 수 있습니다.

  - 인스턴트 메시지 및 오디오 및 비디오 통화-Lync와 Skype 사용자 간의 페더레이션 오디오 및 비디오 통화 및 인스턴트 메시징

  - 현재 상태 공유 — 페더레이션 대화 상대 간의 Exchange 현재 상태 정보

  - 단순 관리 — 조직의 정책 및 표준에 따라 페더레이션 통신을 구성 하기 위한 설정 및 컨트롤

**Q: Lync 배포를 Skype와 연결 하려면 어떻게 해야 합니까?**

**A:** 다음 중 하나에 해당 하는 경우 Skype 연결에 대 한 라이선스가 부여 됩니다.

  - Lync Server (2010 또는 2013)와 Lync Server Standard 클라이언트 액세스 라이선스 ("CALs"; 2010 또는 2013)는 Skype에 연결할 조직의 사용자 및/또는 장치에 해당 합니다. 

  - Lync Online (독립 실행형 라이선스 또는 Office 365 제품군의 일부분)그러나이 서비스 (pic.lync.com)는 Lync Server 및 하이브리드 Lync Server 및 Lync Online 배포를 프로 비전 하는 경우에만 사용할 수 있습니다.Lync Online PIC 프로 비전은 Lync Online Control Panel (LOCP)에서 수행 됩니다.

**Q: Lync 최종 사용자가 Skype 연락처에 연결 하기 위해 수행 해야 하는 작업은 무엇 인가요?**

**A:** 도메인이 활성화 되 고 조직의 Lync 관리자가 해당 기능을 사용 하도록 설정한 후 Lync 사용자는 Lync 클라이언트 내의 대화 상대 목록에 Skype 연락처를 추가할 수 있습니다.

**Q: Lync 연락처에 연결 하기 위해 Skype 최종 사용자가 수행 해야 하는 작업은 무엇입니까?**

**A:** Lync 사용자에 게 연결 하려는 모든 Skype 사용자는 자신의 Skype Id와 연결 된 Microsoft 계정을 포함 하 고 Microsoft 계정을 사용 하 여 로그인 해야 합니다.이는 Skype 클라이언트 내에서 사용 하도록 설정할 수 있습니다.

**Q: Windows Live와의 페더레이션을 계속 사용할 수 있나요?**

**A:** 2012 년 10 월에 시작 하 여 Microsoft가 WLM (Windows Live Messenger) 사용자에 게 도움을 시작 했습니다.Lync는 WLM이 시장에 있는 동안에도 WLM과의 페더레이션을 계속 지원 하지만 추가 Windows Live 도메인 정품 인증은 허용 되지 않습니다.WLM 사용자의 이동은 Mac 용 Skype 6.0 및 Windows에서 사용 하도록 설정 됩니다 (예: Microsoft 계정으로 로그인 할 수 있음) 2012 (w LM과 동일한 자격 증명). Skype에 로그인 하기만 하면 WLM 버디 목록이 자동으로 Skype에 입력 되며, 사용자는 landlines 및 mobiles 통화, 화면 공유, 그룹 비디오 통화, 다양 한 지원 등의 Skype 확장 통신 기능을 활용할 수 있습니다. 다양 한 장치또한 WLM 사용자의 페더레이션 Lync 연락처는 나머지 대화 상대 목록과 함께 Skype로의 전환을 따르고 이러한 연락처에 대해 Skype 및 Lync 간의 IM을 즉시 사용할 수 있습니다. Lync 고객은이 서비스의 연속성을 사용 하기 위해 어떠한 작업도 수행 하지 않아도 됩니다.

**Q: Yahoo\! 또는 AOL을 사용 하는 페더레이션이 여전히 제공 됩니까?**

**A:** 아니요. Yahoo와의 페더레이션\! 및 AOL은 Yahoo를 지원 합니다.\! 및 AOL두 Yahoo에 대해\! 또한 서비스는 2014 년 6 월 30 일에 종료 되었습니다. 

**Q: Lync를 구입 하기 전에 Skype 연결을 평가판으로 사용할 수 있나요?**

**A:** Skype 연결은 평가판으로 제공 되지 않습니다. 평가판 대신 라이선스를 사용 하는 Lync 고객은 서비스를 테스트 하기 위해 등록 하는 것이 좋습니다.

**Q: 프로 비전에 필요한 정보는 무엇입니까?**

**A:** 적격 라이선스에 따라 프로 비전 요청을 제출 하려면 다음이 필요 합니다.

  - Microsoft 계약 번호:
    
      - Microsoft Volume License 지원: Microsoft Volume License 계약 번호
    
      - Microsoft 파트너 네트워크: Headquarter 파트너 ID
    
      - 서비스 공급자 라이선스 계약: 초기 등록 번호
    
      - 대용량 서비스: 제품 등록 번호

  - 액세스에 지 서비스에 대 한 Fqdn (정규화 된 도메인 이름)입니다.
    
      - 하나 이상의 액세스에 지 서비스에 대 한 FQDN이 필요 합니다.
    
      - 조직에 액세스에 지 서비스를 실행 하는 서버가 둘 이상 있는 경우 각 추가 액세스에 지 서비스에 대 한 Fqdn을 지정 합니다. 중요: 이전에 액세스에 지 서비스에 대해 FQDN을 지정 했으며이를 변경 하려는 경우에는 변경에 대 한 프로 비전을 완료 하는 데 며칠 정도 걸릴 수 있으며 서비스가 중단 될 수 있습니다. 서비스 중단을 방지 하려면 액세스에 지 서비스에 대해 이전에 지정 된 FQDN을 유지 관리 하는 것이 좋습니다.

  - SIP (Session 착수 프로토콜) 도메인 사용자가 현재 인스턴트 메시징에 사용 하는 SIP URI의 도메인 접미사입니다. 조직에 둘 이상의 SIP 도메인이 있는 경우 인스턴트 메시징에 사용 되는 각 도메인에 대 한 도메인 접미사를 지정 합니다. 예를 들어 user1@contoso.com의 경우 SIP 도메인에 대해 contoso.com를 지정 합니다. user1@example.fabrikam.com의 경우 example.fabrikam.com을 SIP 도메인으로 지정 합니다.
    
    <div>
    

    > [!NOTE]
    > SIP 도메인에 대 한 도메인 접미사만 지정 합니다. 액세스에 지 서비스에 대 한 FQDN을 포함 하 여 SIP 도메인에 대해서는 fqdn을 지정 하지 마세요.

    
    </div>

  - 연락처 정보 지정 하는 각 SIP 도메인의 관리자에 대 한 전자 메일 주소를 지정 합니다.

**Q: 분할 도메인 시나리오에서 Lync-Skype 연결을 사용 하도록 설정 하려면 어떻게 해야 합니까?**

**A:** Lync Online 2013 및 Lync Server 온-프레미스 분할 도메인 (사용자가 같은 SIP 도메인을 사용 하 여 온라인 및 온-프레미스 모두)이 있는 경우 다음 두 단계를 수행 하 여 Lync Skype 연결을 다음 순서로 사용 하도록 설정 합니다.

1.  PIC 프로 비전 가이드에 설명 된 대로 온-프레미스 Lync Skype 연결을 설정 합니다.

2.  Microsoft에서 도메인을 프로 비전 한 것으로 확인 될 때까지 기다립니다.

3.  확인이 나타나면 Lync 관리 센터를 사용 하 여 "외부 통신"을 설정 합니다. 자세한 내용은[http://office.microsoft.com/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](http://office.microsoft.com/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356)

이 순서는 중요 합니다.Lync Online에서 통신을 사용 하도록 설정 하기 전에 온-프레미스 연결을 설정 해야 합니다. 순서가 거꾸로 된 경우 온-프레미스 <https://pic.lync.com> 에 입력 한 정보는 이동 하지 않습니다. 이 도메인과의 외부 통신에 대해 Lync Online을 이미 설정한 경우에는이 기능을 해제 하 고 24 시간 동안 기다린 후에 온-프레미스 정보 <https://pic.lync.com> 를 입력 한 다음 Lync Online에 대 한 외부 통신을 설정 하 여 다시 시작 해야 합니다.

**Q: Skype 연결용으로 여러 액세스에 지 서비스 Fqdn을 프로 비전 할 수 있나요?**

**A:** 하나 이상의 도메인에 대해 하나의 액세스에 지 FQDN을 프로 비전 할 수 있습니다. 개별 도메인을 사용 하는 경우 요청당 최대 10 개의 액세스에 지 Fqdn을 프로 비전 할 수 있습니다.

**Q: 프로 비전을 요청 하는 조직에서 찾은 Microsoft 계정 전자 메일 주소 목록을 얻을 수 있나요?**

**A:** 아니요. 이러한 주소는 개인 식별이 가능한 정보로 간주 되며 공유 되지 않습니다.

**Q: Windows Live에서 지원 하지 않는 도메인을 포함 하는 ID가 있는 Windows Live Messenger 연락처를 추가 하는 방법은 무엇 인가요?**

**A:** 계정이 나 ID가 windows live가 아닌 다른 도메인을 사용 하 여 windows live Messenger 사용자를 추가 하 \<는 경우 주소를 사용자 이름\>(도메인 이름\<\>) @msn .com으로 입력 합니다 ( \<도메인 이름은\> 사용자의 전자 메일 주소에 있는 도메인 이름). 예를 들어 ted@contoso.com를 추가 하려면 ted (contoso) @msn .com을 사용 합니다. Windows Live를 통해 관리 되는 도메인 목록은 "Live Communications Server 서비스 팩 1을 설치한 후 공용 인스턴트 메시징에서 발생 하는 알려진 문제"의 지원 되는 도메인 섹션을 참조 https://support.microsoft.com/?kbid=897567하세요.

**Q: 프로 비전 프로세스는 얼마 동안 소요 됩니까?**

**A:** 프로 비전에 최대 30 일이 걸릴 수 있습니다.

**Q: 프로비저닝이 완료 되 면 어떻게 확인 됩니까?**

**A:** Microsoft는 프로비저닝이 완료 되 면 전자 메일 알림을 보냅니다.

**Q: 제출 하는 구성 또는 연락처 세부 정보를 업데이트 하려면 어떻게 해야 하나요?**

**A:** 구축이 완료 된 후 프로 비전을 요청 하는 데 사용한 것과 동일한 웹 사이트에서 정보를 업데이트할 수 있습니다. 계약 번호를 입력 한 다음 서비스 업데이트를 클릭 합니다.

</div>

<span> </span>

</div>

</div>

</div>

