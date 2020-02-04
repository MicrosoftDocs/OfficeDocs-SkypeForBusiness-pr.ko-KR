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

# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a><span data-ttu-id="e2563-102">Lync Server 2013에서 XmlAdapter를 사용자 지정 된 영구 채팅 서버 준수 어댑터로 바꾸기</span><span class="sxs-lookup"><span data-stu-id="e2563-102">Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2563-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e2563-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e2563-104">영구 채팅 서버와 함께 설치 된 XmlAdapter를 사용 하는 대신 사용자 지정 어댑터를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2563-104">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="e2563-105">이를 수행 하려면 **IComplianceAdapter** 인터페이스를 구현 하는 공용 클래스를 포함 하는 .net Framework 어셈블리를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2563-105">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="e2563-106">이 어셈블리는 영구 채팅 서버 풀에 있는 각 서버의 영구 채팅 서버 설치 폴더에 배치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2563-106">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="e2563-107">규정 준수 서버 중 하나가 어댑터에 준수 데이터를 제공할 수 있지만, 규정 준수 서버는 어댑터의 여러 인스턴스에 대 한 중복 준수 데이터를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2563-107">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a><span data-ttu-id="e2563-108">IComplianceAdapter 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="e2563-108">Implementing the IComplianceAdapter interface</span></span>

<span data-ttu-id="e2563-109">인터페이스는 네임 스페이스 `Microsoft.Rtc.Internal.Chat.Server.Compliance`의 준수 .dll 어셈블리에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2563-109">The interface is defined in the Compliance.dll assembly in the namespace `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="e2563-110">인터페이스는 사용자 지정 어댑터에서 구현 해야 하는 두 가지 메서드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2563-110">The interface defines two methods that your custom adapter must implement.</span></span>

    void SetConfig(AdapterConfig config)

<span data-ttu-id="e2563-111">영구 채팅 준수 서버는 어댑터가 처음 로드 될 때이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2563-111">The Persistent Chat Compliance server will call this method when the adapter first loads.</span></span> <span data-ttu-id="e2563-112">에 `AdapterConfig` 는 준수 어댑터와 관련 된 지속적인 채팅 준수 구성이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2563-112">The `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter.</span></span>

    void Translate(ConversationCollection conversations)

<span data-ttu-id="e2563-113">영구적 채팅 준수 서버는 변환할 새 데이터가 있는 동안 정기적으로이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2563-113">The Persistent Chat Compliance server calls this method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="e2563-114">이 시간 간격은 영구 채팅 준수 구성 `RunInterval` 에 설정 된 as와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2563-114">This time interval is equal to the `RunInterval` as set in the Persistent Chat Compliance configuration.</span></span>

<span data-ttu-id="e2563-115">에 `ConversationCollection` 는이 메서드를 마지막으로 호출 했을 때 수집 된 대화 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2563-115">The `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

