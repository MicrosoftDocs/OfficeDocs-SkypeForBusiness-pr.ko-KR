---
title: 'Lync Server 2013: 사용자 지정 된 영구 채팅 서버 준수 어댑터로 XmlAdapter 교체'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter
ms:assetid: 2cb70db2-663f-40a6-abcf-89ea7d4a8b65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ680106(v=OCS.15)
ms:contentKeyID: 49558152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e9cd9f2e950e835a113f64795022753e44e3ff5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a>Lync Server 2013에서 XmlAdapter를 사용자 지정 된 영구 채팅 서버 준수 어댑터로 바꾸기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

영구 채팅 서버와 함께 설치 되는 XmlAdapter를 사용 하는 대신 사용자 지정 어댑터를 작성할 수 있습니다. 이렇게 하려면 **IComplianceAdapter** 인터페이스를 구현하는 공용 클래스가 포함된 .NET Framework 어셈블리를 제공해야 합니다. 영구 채팅 서버 풀에 있는 각 서버의 영구 채팅 서버 설치 폴더에이 어셈블리를 배치 해야 합니다. 준수 서버 중 하나가 어댑터에 준수 데이터를 제공할 수 있지만, 준수 서버가 여러 어댑터 인스턴스에 대해 중복 준수 데이터를 제공하지는 않습니다.

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a>IComplianceAdapter 인터페이스 구현

인터페이스는 네임 스페이스 `Microsoft.Rtc.Internal.Chat.Server.Compliance`의 준수 .dll 어셈블리에 정의 됩니다. 이 인터페이스는 사용자 지정 어댑터가 구현해야 하는 두 개의 메서드를 정의합니다.

    void SetConfig(AdapterConfig config)

영구 채팅 준수 서버는 어댑터가 처음 로드 될 때이 메서드를 호출 합니다. 에 `AdapterConfig` 는 준수 어댑터와 관련 된 영구 채팅 준수 구성이 포함 되어 있습니다.

    void Translate(ConversationCollection conversations)

영구적 채팅 준수 서버는 변환할 새 데이터가 있는 동안 주기적으로이 메서드를 호출 합니다. 이 시간 간격은 영구 채팅 준수 구성 `RunInterval` 에서 설정 하는 것과 같습니다.

에 `ConversationCollection` 는이 메서드를 마지막으로 호출한 시간에서 수집 된 대화 정보가 포함 됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

