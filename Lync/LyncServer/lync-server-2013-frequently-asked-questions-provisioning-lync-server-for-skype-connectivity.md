---
title: '질문과 대답: Skype 연결을 위한 Lync Server 프로비전'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Frequently Asked Questions: Provisioning Lync Server for Skype connectivity'
ms:assetid: 4d1b2bfc-780b-4b8c-afd5-11c2e59203b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440172(v=OCS.15)
ms:contentKeyID: 57793362
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fc06cda300945ccf4d7da9424b5615028c2e8f5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="frequently-asked-questions-provisioning-lync-server-2013-for-skype-connectivity"></a>질문과 대답: Skype 연결을 위한 Lync Server 2013 프로비전

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2019-03-22_

2019 년 4 월부터 시작 해 서 pic.lync.com 웹 사이트를 통해 Skype Federation 용으로 프로 비전 된 고객에 대 한 연락처 정보의 수집 및 보존이 중지 됩니다. 이 변경 사항은 pic.lync.com 프로비저닝 시스템이 Microsoft 개인정보 보호 정책을 준수 하도록 하기 위한 것입니다. 
 
이 변경이 실시간으로 진행 되 면 보류 중인 프로 비전 변경 내용에 대 한 전자 메일 업데이트를 더 이상 제공할 수 없게 됩니다. PIC 프로 비전 변경 사항은 일반적으로 입력 후 24-48 시간 내에 완료 됩니다. 프로비저닝 요청을 제출한 후에도 여전히 Skype 페더레이션 문제 48 시간이 발생 하는 경우에는 Microsoft 기술 지원 서비스에 문의 하 여 더 자세히 조사 하세요.

> [!IMPORTANT]
> 이 변경 사항으로 인해 이전에 입력 한 모든 연락처 정보는 2019 년 5 월 말까지 시스템에서 제거 됩니다.


**Q: Microsoft Lync와 Skype 간에 지원 되는 기능은 무엇입니까?**

**A:** Microsoft 가족의 Skype를 사용 하는 경우, Skype를 사용 하는 수백 명에 게 통합 커뮤니케이션 시나리오를 확장 하기 위해 새로운 가능성을 열 수 있습니다. Lync 고객은이 조합을 통해 공급자, 고객, 파트너와 연결 하 고 공동 작업을 할 수 있습니다.

  - 인스턴트 메시지 및 오디오, 영상 통화-Lync와 Skype 사용자 간 연결 된 오디오 및 비디오 통화 및 인스턴트 메시지

  - 현재 상태 공유 — 페더레이션 대화 상대 간의 교환 현재 상태 정보

  - 간단한 관리 — 조직의 정책 및 표준에 따라 페더레이션 통신을 구성 하는 설정 및 컨트롤

**Q: Lync 배포를 Skype와 연결 하려면 어떻게 해야 하나요?**

**A:** 다음 중 하나가 있는 경우 Skype 연결에 대 한 라이선스가 부여 됩니다.

  - Lync Server (2010 또는 2013)와 Lync Server Standard 클라이언트 액세스 라이선스 ("CALs"; 2010 또는 2013)는 Skype에 연결 하는 조직의 사용자 및/또는 장치에 사용 합니다. 

  - Lync Online (독립 실행형 라이선스 또는 Office 365 제품군의 일부).그러나이 서비스 (pic.lync.com)는 Lync Server를 프로 비전 하 고 하이브리드 Lync Server 및 Lync Online 배포에만 해당 됩니다.Lync Online PIC 프로 비전은 Lync Online 제어판 (LOCP)에서 수행 됩니다.

**Q: Lync 최종 사용자는 Skype 연락처에 연결 하기 위해 어떤 작업을 해야 하나요?**

**A:** 도메인이 활성화 되 고 조직의 Lync 관리자가 해당 기능을 사용 하도록 설정한 후 Lync 사용자는 lync 클라이언트 내의 대화 상대 목록에 Skype 연락처를 추가할 수 있습니다.

**Q: Skype 최종 사용자가 Lync 연락처에 연결 하려면 어떻게 해야 하나요?**

**A:** Lync 사용자에 게 연결 하려는 모든 Skype 사용자에 게는 Skype Id와 연결 된 Microsoft 계정이 있어야 하 고 Microsoft 계정을 사용 하 여 로그인 해야 합니다.Skype 클라이언트 내에서이 기능을 사용할 수 있습니다.

**Q: Windows Live와 페더레이션 하는 페더레이션은 계속 사용할 수 있나요?**

**A:** 2012 년 10 월부터 Microsoft가 WLM (Windows Live Messenger) 사용자의 도움을 시작 했습니다. \ 0이 (가) Skype로 이동 하 여 결국 WLM을 폐기 하세요.Lync는 WLM이 시장에 거주 하는 경우에는 계속 해 서 WLM을 지원 하지만 추가 Windows Live 도메인 활성화는 허용 되지 않습니다.W LM 사용자의 이동은 Skype 6.0 (Mac 용) 및 Windows (2012:10 월 25 일 릴리스)가 사용 하 여 Microsoft 계정 (WLM과 동일한 자격 증명)으로 로그인 할 수 있습니다. Skype에 로그인 하면 w LM 친구 목록이 자동으로 Skype에 입력 되며, 사용자는 유선전화 및 휴대폰 통화, 화면 공유, 그룹 영상 통화, 폭넓은 지원 등 Skype의 확장 된 통신 기능을 활용할 수 있습니다. 다양 한 장치.더욱이, WLM 사용자의 페더레이션 Lync 연락처는 나머지 친구 목록과 함께 Skype로의 전환을 따르고 이러한 연락처에 대 한 Skype와 Lync 간의 인스턴트 메시지를 즉시 사용할 수 있습니다. Lync 고객은이 서비스의 연속성을 사용 하기 위해 어떤 작업도 수행할 필요가 없습니다.

**Q: Yahoo\! 또는 AOL의 페더레이션이 여전히 제공 되나요?**

**A:** 아니요. Yahoo와의 페더레이션\! 및 AOL은 Yahoo의 지원으로 부과 되었습니다.\! 및 AOL.두 Yahoo\! 서비스는 2014 년 6 월 30 일에 종료 됩니다. 

**Q: Lync를 구매 하기 전에 Skype 연결을 체험 하나요?**

**A:** Skype 연결은 평가판을 기준으로 제공 되지 않습니다. 평가판을 사용 하는 대신 라이선스를 가진 Lync 고객은 서비스를 테스트 하기 위해 간단히 등록 하는 것이 좋습니다.

**Q: 프로 비전에 필요한 정보는 무엇 인가요?**

**A:** 적격 라이선스 아래에 프로비저닝 요청을 제출 하려면 다음이 필요 합니다.

  - Microsoft 규약 번호:
    
      - Microsoft 볼륨 라이선스 지원: Microsoft 볼륨 라이선스 계약 번호
    
      - Microsoft 파트너 네트워크: Headquarter 파트너 ID
    
      - 서비스 공급자 라이선스 계약: 초기 등록 번호
    
      - 대용량 서비스: 제품 등록 번호

  - 액세스에 지 서비스에 대 한 Fqdn (정규화 된 도메인 이름)입니다.
    
      - 하나 이상의 액세스에 지 서비스에 대 한 FQDN이 필요 합니다.
    
      - 조직에 액세스에 지 서비스를 실행 하는 서버가 두 대 이상 있는 경우 각 추가 액세스에 지 서비스에 대 한 Fqdn을 지정 합니다. 중요: 이전에 액세스 Edge 서비스에 대 한 FQDN을 지정 하 고이를 변경 하려는 경우 변경 내용에 대 한 구축이 완료 될 때까지 며칠 정도 소요 되며 서비스 중단을 초래할 수 있습니다. 서비스 중단을 방지 하려면 이전에 지정 된 액세스 경계 서비스의 FQDN을 유지 하는 것이 좋습니다.

  - SIP (세션 초기화 프로토콜) 도메인. 사용자가 현재 인스턴트 메시지에 사용 하는 SIP URI의 도메인 접미사입니다. 조직에 둘 이상의 SIP 도메인이 있는 경우 인스턴트 메시지에 사용 되는 각 도메인의 도메인 접미사를 지정 합니다. 예를 들어 user1@contoso.com의 경우 SIP 도메인에 대해 contoso.com를 지정 합니다. user1@example.fabrikam.com의 경우 SIP 도메인으로 example.fabrikam.com를 지정 합니다.
    
    <div>
    

    > [!NOTE]
    > SIP 도메인에 대 한 도메인 접미사만 지정 합니다. SIP 도메인에 대해 액세스에 지 서비스의 FQDN을 포함 하 여 fqdn을 지정 하지 마세요.

    
    </div>

  - 연락처 정보. 지정 하는 각 SIP 도메인의 관리자에 대 한 전자 메일 주소를 지정 합니다.

**Q: 분할-도메인 시나리오에서 Lync-Skype 연결을 설정 하려면 어떻게 하나요?**

**A:** Lync Online 2013 및 Lync Server 온-프레미스 분할 도메인 시나리오 (동일한 SIP 도메인을 사용 하는 온라인 및 온-프레미스 사용자)가 있는 경우 다음 두 단계를 순서 대로 수행 하 여 Lync-Skype 연결을 사용 하도록 설정 합니다.

1.  PIC 프로비저닝 가이드에 설명 된 대로 온-프레미스 Lync-Skype 연결을 설정 합니다.

2.  Microsoft에서 도메인을 프로 비전 한 확인이 표시 될 때까지 기다립니다.

3.  확인이 표시 되 면 Lync 관리 센터를 사용 하 여 "외부 통신"을 설정 합니다. 자세한 내용은 다음을 참조 하세요.[http://office.microsoft.com/en-us/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](http://office.microsoft.com/en-us/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356)

이 순서는 중요 합니다.Lync Online에서 통신을 사용 하도록 설정 하기 전에 온-프레미스 연결을 설정 해야 합니다. 주문을 역으로 실행 하면 온-프레미스 <https://pic.lync.com> 에 입력 한 정보가 처리 되지 않습니다. 이 도메인과 외부 통신에 대 한 Lync Online을 이미 설정한 경우에는이를 해제 하 고 24 시간 동안 기다렸다가 다시 시작 하 여 Lync Online에 대 한 온-프레미스 정보 <https://pic.lync.com> 를 입력 한 다음 외부 통신을 설정 합니다.

**Q: Skype 연결에 대 한 복수 액세스 경계 서비스 Fqdn을 프로 비전 할 수 있나요?**

**A:** 하나 이상의 도메인에 대해 액세스에 지 FQDN을 하나만 제공할 수 있습니다. 개별 도메인이 있는 경우 요청당 최대 10 개의 액세스에 지 Fqdn을 제공할 수 있습니다.

**Q: 조직에서 프로 비전을 요청 하는 경우 찾은 Microsoft 계정 전자 메일 주소 목록을 얻을 수 있나요?**

**A:** 아니요. 이러한 주소는 개인 식별이 가능한 정보로 간주 되며 공유 되지 않습니다.

**Q: Windows Live Messenger에서 지원 하지 않는 도메인을 포함 하는 Windows Live Messenger 대화 상대를 추가 하는 방법은 무엇 인가요?**

**A:** Windows live Messenger 사용자를 타사 라이브 도메인이 있는 계정 또는 ID와 함께 추가 하는 경우 주소를 \<사용자 이름\>(도메인 이름\<\>) @msn .com으로 입력 합니다 ( \<도메인 이름은\> 사용자의 전자 메일 주소에 있는 도메인 이름). 예를 들어 ted@contoso.com를 추가 하려는 경우 ted (contoso) @msn .com을 사용 합니다. Windows Live에서 관리 되는 도메인 목록은 "Live Communications Server 서비스 팩 1을 설치한 후 공개 인스턴트 메시지에 발생 하는 알려진 문제"의 지원 되는 도메인 섹션을 참조 http://support.microsoft.com/?kbid=897567하세요.

**Q: 프로 비전 프로세스에 걸리는 시간은 얼마나 되나요?**

**A:** 프로 비전에 최대 30 일이 걸릴 수 있습니다.

**Q: 프로비저닝이 완료 되는 시기는 어떻게 알 수 있나요?**

**A:** Microsoft는 프로비저닝이 완료 되 면 전자 메일 알림을 보냅니다.

**Q: 제출 하는 구성 또는 연락처 정보를 업데이트 하려면 어떻게 하나요?**

**A:** 프로 비전이 완료 된 후 프로 비전을 요청 하는 데 사용한 것과 동일한 웹 사이트에서 정보를 업데이트할 수 있습니다. 계약 번호를 입력 한 다음 서비스 업데이트를 클릭 합니다.

</div>

<span> </span>

</div>

</div>

</div>

