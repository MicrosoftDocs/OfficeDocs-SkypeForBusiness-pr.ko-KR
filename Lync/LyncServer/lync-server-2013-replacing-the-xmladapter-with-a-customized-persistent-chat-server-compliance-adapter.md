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
ms.openlocfilehash: aa0c1e001270e7a51e35d857625c77146f9a62e1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138769"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a><span data-ttu-id="bf3e5-102">Lync Server 2013에서 XmlAdapter를 사용자 지정 된 영구 채팅 서버 준수 어댑터로 바꾸기</span><span class="sxs-lookup"><span data-stu-id="bf3e5-102">Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf3e5-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bf3e5-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bf3e5-104">영구 채팅 서버와 함께 설치 되는 XmlAdapter를 사용 하는 대신 사용자 지정 어댑터를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf3e5-104">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="bf3e5-105">이렇게 하려면 **IComplianceAdapter** 인터페이스를 구현하는 공용 클래스가 포함된 .NET Framework 어셈블리를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf3e5-105">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="bf3e5-106">영구 채팅 서버 풀에 있는 각 서버의 영구 채팅 서버 설치 폴더에이 어셈블리를 배치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf3e5-106">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="bf3e5-107">준수 서버 중 하나가 어댑터에 준수 데이터를 제공할 수 있지만, 준수 서버가 여러 어댑터 인스턴스에 대해 중복 준수 데이터를 제공하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf3e5-107">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a><span data-ttu-id="bf3e5-108">IComplianceAdapter 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="bf3e5-108">Implementing the IComplianceAdapter interface</span></span>

<span data-ttu-id="bf3e5-109">인터페이스는 네임 스페이스 `Microsoft.Rtc.Internal.Chat.Server.Compliance`의 준수 .dll 어셈블리에 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf3e5-109">The interface is defined in the Compliance.dll assembly in the namespace `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="bf3e5-110">이 인터페이스는 사용자 지정 어댑터가 구현해야 하는 두 개의 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bf3e5-110">The interface defines two methods that your custom adapter must implement.</span></span>

    void SetConfig(AdapterConfig config)

<span data-ttu-id="bf3e5-111">영구 채팅 준수 서버는 어댑터가 처음 로드 될 때이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf3e5-111">The Persistent Chat Compliance server will call this method when the adapter first loads.</span></span> <span data-ttu-id="bf3e5-112">에 `AdapterConfig` 는 준수 어댑터와 관련 된 영구 채팅 준수 구성이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf3e5-112">The `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter.</span></span>

    void Translate(ConversationCollection conversations)

<span data-ttu-id="bf3e5-113">영구적 채팅 준수 서버는 변환할 새 데이터가 있는 동안 주기적으로이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf3e5-113">The Persistent Chat Compliance server calls this method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="bf3e5-114">이 시간 간격은 영구 채팅 준수 구성 `RunInterval` 에서 설정 하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bf3e5-114">This time interval is equal to the `RunInterval` as set in the Persistent Chat Compliance configuration.</span></span>

<span data-ttu-id="bf3e5-115">에 `ConversationCollection` 는이 메서드를 마지막으로 호출한 시간에서 수집 된 대화 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf3e5-115">The `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

