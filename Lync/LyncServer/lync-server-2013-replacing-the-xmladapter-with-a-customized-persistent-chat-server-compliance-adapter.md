---
title: 'Lync Server 2013: XmlAdapter를 사용자 지정 된 영구 채팅 서버 준수 어댑터로 바꾸기'
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
ms.openlocfilehash: 9235c57a055131049251d17b75f73a4370cc5f2c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746688"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a>Lync Server 2013에서 XmlAdapter를 사용자 지정 된 영구 채팅 서버 준수 어댑터로 바꾸기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

영구 채팅 서버와 함께 설치 된 XmlAdapter를 사용 하는 대신 사용자 지정 어댑터를 작성할 수 있습니다. 이를 수행 하려면 **IComplianceAdapter** 인터페이스를 구현 하는 공용 클래스를 포함 하는 .net Framework 어셈블리를 제공 해야 합니다. 이 어셈블리는 영구 채팅 서버 풀에 있는 각 서버의 영구 채팅 서버 설치 폴더에 배치 해야 합니다. 규정 준수 서버 중 하나가 어댑터에 준수 데이터를 제공할 수 있지만, 규정 준수 서버는 어댑터의 여러 인스턴스에 대 한 중복 준수 데이터를 제공 하지 않습니다.

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a>IComplianceAdapter 인터페이스 구현

인터페이스는 네임 스페이스 `Microsoft.Rtc.Internal.Chat.Server.Compliance`의 준수 .dll 어셈블리에 정의 되어 있습니다. 인터페이스는 사용자 지정 어댑터에서 구현 해야 하는 두 가지 메서드를 정의 합니다.

    void SetConfig(AdapterConfig config)

영구 채팅 준수 서버는 어댑터가 처음 로드 될 때이 메서드를 호출 합니다. 에 `AdapterConfig` 는 준수 어댑터와 관련 된 지속적인 채팅 준수 구성이 포함 되어 있습니다.

    void Translate(ConversationCollection conversations)

영구적 채팅 준수 서버는 변환할 새 데이터가 있는 동안 정기적으로이 메서드를 호출 합니다. 이 시간 간격은 영구 채팅 준수 구성 `RunInterval` 에 설정 된 as와 동일 합니다.

에 `ConversationCollection` 는이 메서드를 마지막으로 호출 했을 때 수집 된 대화 정보가 포함 됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

