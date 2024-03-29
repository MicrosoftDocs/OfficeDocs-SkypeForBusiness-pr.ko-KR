---
title: '비즈니스용 Skype 서버: 미디어 우회를 통해 트렁크 구성'
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
description: '요약: 미디어 우회가 사용하도록 설정된 트렁크를 구성하고 비즈니스용 Skype 서버. 이렇게 하면 SIP 트렁크 공급자가 중재 서버를 지원하고 있는 것으로 보아 중재 서버 수를 최소화할 수 있습니다.'
---

# <a name="skype-for-business-server-configure-a-trunk-with-media-bypass"></a>비즈니스용 Skype 서버: 미디어 우회를 통해 트렁크 구성

**요약:** 미디어 우회를 사용하도록 설정된 트렁크를 구성하고 비즈니스용 Skype 서버. 이렇게 하면 SIP 트렁크 공급자가 중재 서버를 지원하고 있는 것으로 보아 중재 서버 수를 최소화할 수 있습니다.

다음 단계에 따라 미디어 우회가 사용하도록 설정된 트렁크를 구성합니다. 미디어 우회를 사용하지 않도록 설정하여 트렁크를 구성하기 위해 다음을 참조하여 미디어 우회 없이 트렁크 [구성을 비즈니스용 Skype 서버](configure-trunk-without-media-bypass.md).

미디어 바이패스는 배포할 중재 서버 수를 최소화할 때 유용합니다. 자세한 내용은 [Plan for media bypass in 비즈니스용 Skype](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)

미디어 우회를 사용하도록 설정하는 것이 좋습니다. 그러나 SIP 트렁크에서 미디어 우회를 사용하도록 설정하기 전에 적격 SIP 트렁크 공급자가 미디어 우회를 지원하고 시나리오를 성공적으로 사용하도록 설정하기 위한 요구 사항을 수용할 수 있도록 합니다. 특히 공급자는 조직의 내부 네트워크에 있는 서버의 IP 주소가 있어야 합니다.

> [!NOTE]
> 미디어 우회는 모든 PSTN(Public Switched Telephone Network) 게이트웨이, IP-PBX 및 SBC(Session Border Controller)와 상호 연결되지 않습니다. Microsoft는 인증된 파트너와 함께 PSTN 게이트웨이 및 SBC 집합을 테스트했습니다. 미디어 우회는 전화 통신 인프라 페이지에 나열된 제품 및 버전에서 [비즈니스용 Skype 서버 지원됩니다](../../../SfbPartnerCertification/certification/infra-gateways.md).

아래에 설명된 트렁크 구성은 이 트렁크 구성에 할당된 트렁크에 적용되는 매개 변수 집합을 그룹화합니다. 특정 트렁크 구성의 범위를 전역으로(특정 사이트 또는 풀 구성을 포함하지 않는 모든 트렁크가 포함됨) 또는 사이트나 풀로 지정할 수 있습니다. 풀 수준 트렁크 구성은 특정 트렁크 구성의 범위를 단일 트렁크로 지정하는 데 사용됩니다.

### <a name="to-configure-a-trunk-with-media-bypass"></a>미디어 우회를 통해 트렁크를 구성

1. Open 비즈니스용 Skype 서버 제어판

2. 왼쪽 탐색 모음에서 **음성 라우팅** 을 클릭한 다음 **트렁크 구성** 을 클릭합니다.

3. **트렁크 구성** 페이지에서 다음 방법 중 하나를 사용하여 트렁크를 구성합니다.

   - 기존 트렁크(예: **전역** 트렁크)를 두 번 클릭하여 **트렁크 구성 편집** 대화 상자를 표시합니다.

   - **새로 만들기** 를 클릭한 다음 새 트렁크 구성의 범위를 선택합니다.

   - **사이트 트렁크**: 사이트 선택에서 이 트렁크 구성에 대한 사이트를 선택한 다음 확인을 **클릭합니다**. 트렁크 구성이 이미 만들어진 사이트는 **사이트 선택** 대화 상자에 표시되지 않습니다. 이 트렁크 구성은 사이트의 모든 트렁크에 적용됩니다.

   - **풀 트렁크**: 이 트렁크 구성이 적용되는 트렁크의 이름을 선택 합니다. 이 트렁크는 토폴로지 작성기에서 정의된 루트 트렁크 또는 추가 트렁크일 수 있습니다. 서비스 **선택에서** 확인을 **클릭합니다**. 트렁크 구성이 이미 만들어진 특정 트렁크는 **서비스 선택** 대화 상자에 표시되지 않습니다.

      > [!NOTE]
      > 트렁크 구성 범위는 선택한 후에 변경할 수 없습니다. > 이름 필드는 트  렁크 구성의 연결된 사이트 또는 서비스의 이름으로 미리 채우며 변경할 수 없습니다.

4. 지원되는 최대 초기 **대화 상자에서 값을 지정합니다**. PSTN(Public Switched Telephone Network) 게이트웨이, IP-PBX 또는 ITSP SBC(Session Border Controller)가 INVITE에 수신하여 중재 서버로 보낼 수 있는 최대 포크 응답 수입니다. 기본값은 20입니다.

    > [!NOTE]
    > 이 값을 변경하기 전에 서비스 공급자나 장치 제조업체에 시스템 용량에 대한 자세한 내용을 문의하십시오.

5. 다음 **암호화 지원 수준** 옵션 중 하나를 선택합니다.

   - **필수**: SRTP(Secure Real-Time Transport Protocol) 암호화를 사용하여 중재 서버와 게이트웨이 또는 PBX(Private Branch Exchange) 간의 트래픽을 보호해야 합니다.

   - **선택**: 서비스 공급자 또는 OEM에서 지원하는 경우 SRTP 암호화를 사용합니다.

   - **지원되지 않음**: 서비스 공급자 또는 OEM에서 지원하지 않으므로 SRTP 암호화를 사용할 수 없습니다.

6. 트렁크 피어가 처리하도록 미디어가 중재 서버를 바이패스하도록 하려면 **미디어 바이패스 사용** 확인란을 선택합니다.

    > [!IMPORTANT]
    > 미디어 바이패스가 올바르게 작동하려면 PSTN 게이트웨이, IP-PBX 또는 ITSP 세션 경계 컨트롤러가 특정 기능을 지원해야 합니다. 자세한 내용은 [Plan for media bypass in 비즈니스용 Skype](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

7. 알려진 미디어 종료 지점(예: 미디어 종료 IP가 신호 종료 IP와 같은 PSTN 게이트웨이)이 있는 경우 **중앙 집중식 미디어 처리** 확인란을 선택합니다. 트렁크에 알려진 미디어 종료 지점이 없는 경우에는 이 확인란의 선택을 취소합니다.

8. 트렁크 피어가 중재 서버에서 SIP REFER 요청 수신을 지원하는 경우 게이트웨이 참조 보내기 사용 확인 **란을 선택합니다** .

    > [!NOTE]
    > **미디어 바이패스 사용** 옵션을 선택한 상태에서 이 옵션을 사용하지 않도록 설정하면 추가 설정이 필요합니다. 트렁크 피어가 중재 서버로부터의 SIP REFER 요청 수신을 지원하지 않는데 미디어 바이패스를 사용하는 경우 미디어 바이패스에 대한 적절한 조건을 지원하기 위해 **Set-CsTrunkConfiguration** cmdlet도 실행하여 활성 및 대기 중인 통화에 대해 RTCP를 사용하지 않도록 설정해야 합니다. 또는 전송된 통화를 미디어  를 무시하고 게이트웨이가 SIP REFER 요청을 지원하지 않는 경우 타사 통화 제어를 사용하여 참조 사용을 선택할 수 있습니다.

9. 원하는 경우 트렁크 간 라우팅을 사용하도록 설정하려면 PSTN 사용 레코드를 이 트렁크 구성에 연결하고 구성합니다. 이 트렁크 구성에 연결된 PSTN 사용은 트렁크 끝점에서 시작되지 않는 트렁크를 통해 들어오는 모든 호출에 비즈니스용 Skype 서버 적용됩니다. 트렁크 구성에 연결된 PSTN 사용 레코드를 관리하려면 다음 방법 중 하나를 사용합니다.

   - 사용자 배포에서 사용할 수 있는 모든 PSTN 사용 레코드 목록에서 하나 Enterprise Voice 선택을 **클릭합니다**. 이 트렁크 구성과 연결할 레코드를 강조 표시하고 **확인** 을 클릭합니다.

   - 이 트렁크 구성에서 PSTN 사용 레코드를 제거하려면 레코드를 강조 표시하고 **제거** 를 클릭합니다.

   - 새 PSTN 사용 레코드를 정의하고 이 트렁크 구성과 연결하려면 다음을 수행합니다.

     a. **새로 만들기** 를 클릭합니다.

     b. **이름** 필드에서 레코드를 설명하는 고유한 이름을 지정합니다.

     > [!NOTE]
     > PSTN 사용 레코드 이름은 PSTN 배포 내에서 고유해야 Enterprise Voice 합니다. 레코드를 저장한 후에는 **이름** 필드를 편집할 수 없습니다.

     c. 다음 방법 중 하나를 사용하여 이 PSTN 사용 레코드에 대한 경로를 구성하고 연결합니다.

     - 사용자 지정 배포에서 사용 가능한 모든 경로 목록에서 하나 Enterprise Voice 선택을 **클릭합니다**. 이 PSTN 사용 레코드와 연결할 경로를 강조 표시한 다음 **확인** 을 클릭합니다.

     - PSTN 사용 레코드에서 경로를 제거하려면 경로를 선택하고 **제거** 를 클릭합니다.

   - 새 경로를 정의하고 이 PSTN 사용 레코드와 연결하려면 **새로 만들기** 를 클릭합니다. 자세한 내용은 [Create or modify a voice route in 비즈니스용 Skype](create-or-modify-a-voice-route.md).

     - 이 PSTN 사용 레코드에 연결된 경로를 편집하려면 경로를 선택하고 **자세한 정보 표시** 를 클릭합니다.

     d. **확인** 을 클릭합니다.

     - 이 트렁크 구성에 이미 연결된 PSTN 사용 레코드를 편집하려면 다음을 수행합니다.

       a. 편집할 PSTN 사용 레코드를 선택하고 **자세한 정보 표시** 를 클릭합니다.

       b. 다음 방법 중 하나를 사용하여 이 PSTN 사용 레코드에 대한 경로를 구성하고 연결합니다.

   - 사용자 지정 배포에서 사용 가능한 모든 경로 목록에서 하나 Enterprise Voice 선택을 **클릭합니다**. 이 PSTN 사용 레코드와 연결할 경로를 강조 표시한 다음 **확인** 을 클릭합니다.

   - PSTN 사용 레코드에서 경로를 제거하려면 경로를 선택하고 **제거** 를 클릭합니다.

   - 새 경로를 정의하고 이 PSTN 사용 레코드와 연결하려면 **새로 만들기** 를 클릭합니다. 자세한 내용은 [Create or modify a voice route in 비즈니스용 Skype](create-or-modify-a-voice-route.md).

   - 이 PSTN 사용 레코드에 연결된 경로를 편집하려면 경로를 선택하고 **자세한 정보 표시** 를 클릭합니다.

     c. **확인** 을 클릭합니다.

     > [!IMPORTANT]
     > 구성되는 트렁크와 연결된 중재 서버 피어에 따라 PSTN 사용 레코드를 연결해야 합니다. 중재 서버 피어가 PSTN 게이트웨이 또는 SBC(Session Border Controller)인 경우 트렁크 구성이 PSTN 대상 또는 PSTN을 통해 연결된 다른 다운스트림 시스템으로 라우팅되는 PSTN 사용 레코드에 연결되지 비즈니스용 Skype 서버.

10. 최적의 성능을 유지하도록 PSTN 사용 레코드를 정렬합니다. 목록에서 레코드의 위치를 변경하려면 PSTN 사용 레코드를 선택하고 위쪽 또는 아래쪽 화살표를 클릭합니다.

    > [!IMPORTANT]
    > PSTN 사용 레코드가 트렁크 구성에서 나열되는 순서가 중요합니다. 비즈니스용 Skype 서버 목록이 위쪽에서 아래로 트래버스됩니다.

11. NAT(Network Address Translation) 또는 방화벽 뒤에 있는 클라이언트와 래치 기능을 지원하는 SBC에 대해 미디어를 우회하도록 설정하려면 **RTP 래** 치 사용이 선택되어 있습니다.

12. **통화 기록 정보를** 중재 서버의 게이트웨이 피어로 보낼 수 있도록 설정하려면 전달 통화 기록 사용이 선택되어 있습니다.

13. PAI(P-Asserted-Identity) 통화 발신자 정보를 중재 서버 쪽과 게이트웨이 쪽(또는 그 반대의 경우) 간에 전달할 수 있도록 설정하려면 **P-Asserted-Identity** 데이터를 전달하도록 설정해야 합니다.

14. 빠른 장애 조치(failover)를 사용하도록 설정하려면 **아웃바운드 라우팅 장애 조치(failover) 타이머 사용** 을 선택해야 합니다. 이 트렁크와 연결된 게이트웨이는 아웃바운드 통화를 처리하는 10초 이내에 알림을 제공할 수 있습니다. 중재 서버에서 이 알림을 받지 못하면 다른 트렁크로 다시 로우트됩니다. 대기 시간으로 인해 응답 시간이 지연되거나 게이트웨이가 응답하는 데 10초보다 오래 걸리는 네트워크에서는 빠른 장애 조치(failover)를 사용하지 않도록 설정해야 합니다.

15. 원하는 경우 트렁크에 대해 **호출 번호 변환 규칙** 을 연결 및 구성합니다. 이러한 변환 규칙은 아웃바운드 통화의 호출 번호에 적용됩니다.

    - 사용자 지정 배포에서 사용할 수 있는 모든 변환 규칙 목록에서 하나 Enterprise Voice 선택을 **클릭합니다**. **변환 규칙 선택** 에서 트렁크와 연결할 규칙을 클릭한 다음 **확인** 을 클릭합니다.

    - 새 변환 규칙을 정의하고 트렁크와 연결하려면 **새로 만들기** 를 클릭합니다. 변환 규칙에 대한 자세한 내용은 Translation [rules in 비즈니스용 Skype 서버](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).

    - 트렁크와 이미 연결된 변환 규칙을 편집하려면 규칙 이름을 클릭한 다음 **자세한 정보 표시** 를 클릭합니다.

    - 기존 변환 규칙을 복사하여 새 규칙을 정의하는 시작 시점으로 사용하려면 규칙 이름을 클릭하고 **복사** 를 클릭한 다음 **붙여넣기** 를 클릭합니다.

    - 트렁크에서 변환 규칙을 제거하려면 규칙 이름을 강조 표시하고 **제거** 를 클릭합니다.

    > [!CAUTION]
    > 연결된 트렁크 피어에서 변환 규칙을 구성한 경우에는 두 규칙이 충돌할 수 있으므로 변환 규칙을 트렁크와 연결하지 마십시오.

16. 원하는 경우 트렁크에 대해 **호출된 번호 변환 규칙** 을 연결 및 구성합니다. 변환 규칙은 아웃바운드 통화의 호출된 번호에 적용됩니다.

    - 사용자 지정 배포에서 사용할 수 있는 모든 변환 규칙 목록에서 하나 Enterprise Voice 선택을 **클릭합니다**. **변환 규칙 선택** 에서 트렁크와 연결할 규칙을 클릭한 다음 **확인** 을 클릭합니다.

    - 새 변환 규칙을 정의하고 트렁크와 연결하려면 **새로 만들기** 를 클릭합니다. 변환 규칙에 대한 자세한 내용은 Translation [rules in 비즈니스용 Skype 서버](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).

    - 트렁크와 이미 연결된 변환 규칙을 편집하려면 규칙 이름을 클릭한 다음 **자세한 정보 표시** 를 클릭합니다.

    - 기존 변환 규칙을 복사하여 새 규칙을 정의하는 시작 시점으로 사용하려면 규칙 이름을 클릭하고 **복사** 를 클릭한 다음 **붙여넣기** 를 클릭합니다.

    - 트렁크에서 변환 규칙을 제거하려면 규칙 이름을 강조 표시하고 **제거** 를 클릭합니다.

    > [!CAUTION]
    > 연결된 트렁크 피어에서 변환 규칙을 구성한 경우에는 두 규칙이 충돌할 수 있으므로 변환 규칙을 트렁크와 연결하지 마십시오.

17. 트렁크의 변환 규칙이 올바른 순서로 정렬된지 확인합니다. 목록에서 규칙의 위치를 변경하려면 규칙 이름을 강조 표시한 다음 위쪽 또는 아래쪽 화살표를 클릭합니다.

    > [!IMPORTANT]
    > 비즈니스용 Skype 서버 맨 아래에서 변환 규칙 목록을 트래버스하고 전화 걸기 번호와 일치하는 첫 번째 규칙을 사용 합니다. 전화를 건 번호가 둘 이상의 변환 규칙과 일치할 수 있도록 트렁크를 구성하는 경우에는 제약이 많은 규칙이 제약이 적은 규칙보다 위에 정렬되어 있어야 합니다. 예를 들어 11자리 번호와 일치하는 변환 규칙과 +1425로 시작하는 11자리 번호만 일치하는 변환 규칙을 포함한 경우 11자리 번호와 일치하는 규칙이 보다 제한적인 규칙 아래에 정렬해야 합니다.

18. 트렁크 구성을 마쳤으면 **확인** 을 클릭합니다.

19. **트렁크 구성** 페이지에서 **커밋** 을 클릭하고 **모두 커밋** 을 클릭합니다.

    > [!NOTE]
    > 트렁크 구성을 만들거나 수정할 때는 항상 **모두 커밋** 명령을 실행하여 구성 변경 내용을 게시해야 합니다. 자세한 내용은 작업 설명서에서 [Publish pending changes to the voice routing configuration in 비즈니스용 Skype](voice-route-config-changes.md) 참조하십시오.

트렁크를 구성한 후 배포 설명서의 [Deploy media bypass in 비즈니스용 Skype 서버](deploy-media-bypass.md) 설명된 글로벌 미디어 우회 옵션 중 선택하여 미디어 우회를 계속 구성합니다.
## <a name="see-also"></a>참고 항목

[미디어 우회 없이 트렁크를 구성합니다비즈니스용 Skype 서버](configure-trunk-without-media-bypass.md)

[미디어 우회를 비즈니스용 Skype 서버](deploy-media-bypass.md)

[변환 규칙 정의](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)

[미디어 우회 구성](/previous-versions/office/lync-server-2013/lync-server-2013-configure-media-bypass)