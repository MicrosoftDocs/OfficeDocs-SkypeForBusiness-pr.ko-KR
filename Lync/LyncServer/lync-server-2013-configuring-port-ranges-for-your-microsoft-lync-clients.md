---
title: 'Lync Server 2013: Microsoft Lync 클라이언트에 대 한 포트 범위 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Microsoft Lync clients
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea0300b042dc124f0fb8bf523221e39128cbf57a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a><span data-ttu-id="f0078-102">Lync Server 2013에서 Microsoft Lync 클라이언트에 대 한 포트 범위 구성</span><span class="sxs-lookup"><span data-stu-id="f0078-102">Configuring port ranges for your Microsoft Lync clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0078-103">_**마지막으로 수정 된 항목:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="f0078-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="f0078-104">기본적으로 Lync 클라이언트 응용 프로그램은 통신 세션에 포함 된 경우 포트 1024과 65535 사이의 모든 포트를 사용할 수 있습니다. 이는 특정 포트 범위가 클라이언트에 대해 자동으로 사용 하지 않도록 설정 되었기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="f0078-104">By default, Lync client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="f0078-105">그러나 서비스 품질을 사용 하려면 다양 한 트래픽 유형 (오디오, 비디오, 미디어, 응용 프로그램 공유 및 파일 전송)을 일련의 고유한 포트 범위에 다시 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0078-105">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="f0078-106">이 작업은 Get-csconferencingconfiguration cmdlet을 사용 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0078-106">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f0078-107">최종 사용자는 이러한 변경 작업을 직접 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0078-107">End users cannot make these changes themselves.</span></span> <span data-ttu-id="f0078-108">포트 변경 내용은 Get-csconferencingconfiguration cmdlet을 사용 하는 관리자만 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0078-108">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>



</div>

<span data-ttu-id="f0078-109">Microsoft Lync Server 2013 관리 셸 내에서 다음 명령을 실행 하 여 현재 통신 세션에 사용 되는 포트 범위를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0078-109">You can determine which port ranges are currently used for communication sessions by running the following command from within the Microsoft Lync Server 2013 Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="f0078-110">Lync Server 2013를 설치한 이후에 회의 설정을 변경 하지 않은 경우 다음 속성 값이 포함 된 정보를 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0078-110">Assuming that you have not made any changes to your conferencing settings since you installed Lync Server 2013, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="f0078-111">위의 출력을 자세히 보면 두 가지 중요한 사항을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0078-111">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="f0078-112">먼저, ClientMediaPortRangeEnabled 속성이 False로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0078-112">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="f0078-113">이 속성이 False로 설정 되 면 Lync 클라이언트는 통신 세션에 포함 된 경우 포트 1024과 65535 사이에 사용 가능한 포트를 사용 하기 때문에 중요 합니다. 이는 다른 포트 설정 (예: ClientMediaPort 또는 ClientVideoPort)에 관계 없이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0078-113">That's important because, when this property is set to False, Lync clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="f0078-114">지정 된 포트 집합으로 사용을 제한 하려는 경우 (서비스 품질을 구현 하려는 경우에는이 작업을 수행 하려는 경우) 먼저 클라이언트 미디어 포트 범위를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0078-114">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service) then you must first enable client media port ranges.</span></span> <span data-ttu-id="f0078-115">다음 Windows PowerShell 명령을 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0078-115">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="f0078-p105">위의 명령은 회의 구성 설정의 전역 컬렉션에 대해 클라이언트 미디어 포트 범위를 사용하도록 설정합니다. 그러나 이러한 설정은 사이트 범위 및/또는 서비스 범위(회의 서버 서비스에 한함)에도 적용할 수 있습니다. 특정 사이트 또는 서버에 대해 클라이언트 미디어 포트 범위를 사용하도록 설정하려면 Set-CsConferencingConfiguration을 호출할 때 해당 사이트 또는 서버의 Identity를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0078-p105">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only). To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="f0078-118">또는 이 명령을 사용하여 모든 회의 구성 설정에 대해 포트 범위를 동시에 사용하도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0078-118">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="f0078-119">위의 출력에서 두 번째로 중요한 사항은 예제 출력에서 기본적으로 각 네트워크 트래픽 유형에 대해 설정된 미디어 포트 범위가 동일하다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="f0078-119">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="f0078-p106">QoS를 구현하려면 이러한 각 포트 범위가 고유해야 합니다. 예를 들어 포트 범위를 다음과 같이 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0078-p106">In order to implement QoS, each of these port ranges will need to be unique. For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f0078-122">클라이언트 트래픽 유형</span><span class="sxs-lookup"><span data-stu-id="f0078-122">Client Traffic Type</span></span></th>
<th><span data-ttu-id="f0078-123">포트 시작</span><span class="sxs-lookup"><span data-stu-id="f0078-123">Port Start</span></span></th>
<th><span data-ttu-id="f0078-124">포트 범위</span><span class="sxs-lookup"><span data-stu-id="f0078-124">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0078-125">오디오만</span><span class="sxs-lookup"><span data-stu-id="f0078-125">Audio</span></span></p></td>
<td><p><span data-ttu-id="f0078-126">50020</span><span class="sxs-lookup"><span data-stu-id="f0078-126">50020</span></span></p></td>
<td><p><span data-ttu-id="f0078-127">20cm(8</span><span class="sxs-lookup"><span data-stu-id="f0078-127">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0078-128">비디오</span><span class="sxs-lookup"><span data-stu-id="f0078-128">Video</span></span></p></td>
<td><p><span data-ttu-id="f0078-129">58000</span><span class="sxs-lookup"><span data-stu-id="f0078-129">58000</span></span></p></td>
<td><p><span data-ttu-id="f0078-130">20cm(8</span><span class="sxs-lookup"><span data-stu-id="f0078-130">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0078-131">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="f0078-131">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="f0078-132">42000</span><span class="sxs-lookup"><span data-stu-id="f0078-132">42000</span></span></p></td>
<td><p><span data-ttu-id="f0078-133">20cm(8</span><span class="sxs-lookup"><span data-stu-id="f0078-133">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0078-134">파일 전송</span><span class="sxs-lookup"><span data-stu-id="f0078-134">File transfer</span></span></p></td>
<td><p><span data-ttu-id="f0078-135">42020</span><span class="sxs-lookup"><span data-stu-id="f0078-135">42020</span></span></p></td>
<td><p><span data-ttu-id="f0078-136">20cm(8</span><span class="sxs-lookup"><span data-stu-id="f0078-136">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f0078-p107">위의 표에서 클라이언트 포트 범위는 서버에 대해 구성된 포트 범위의 하위 집합을 나타냅니다. 예를 들어 서버에서 응용 프로그램 공유는 포트 40803~49151을 사용하도록 구성되었습니다. 반면 클라이언트 컴퓨터에서는 응용 프로그램 공유가 포트 42000~42019를 사용하도록 구성되었습니다. 이러한 구성 역시 기본적으로 QoS를 보다 쉽게 관리하기 위한 것입니다. 클라이언트 포트는 서버에서 사용되는 포트의 하위 집합이 아니어도 됩니다. 예를 들어 클라이언트 컴퓨터에서는 응용 프로그램 공유가 포트 10000~10019를 사용하도록 구성할 수도 있습니다. 그러나 클라이언트 포트 범위를 서버 포트 범위의 하위 집합으로 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f0078-p107">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers. For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019. This, too is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server. (For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="f0078-p108">또한 서버에서는 응용 프로그램 공유용으로 포트 8348개가 설정되었는데 클라이언트에서는 응용 프로그램 공유용으로 포트가 20개만 설정되었음을 확인할 수 있습니다. 이러한 구성 역시 사용하는 것이 좋기는 하지만 반드시 지켜야 하는 규칙은 아닙니다. 일반적으로 사용 가능한 각 포트는 단일 통신 세션을 나타낸다고 간주할 수 있습니다. 포트 범위에서 포트 100개를 사용할 수 있으면 해당하는 컴퓨터가 지정된 시간에 최대 100개의 통신 세션에 참가할 수 있다는 의미입니다. 서버는 클라이언트보다 훨씬 많은 대화에 참가하므로 클라이언트보다 서버에 더 많은 수의 포트를 열어 두는 것이 적절합니다. 클라이언트에서 응용 프로그램 공유용으로 포트 20개를 설정하면 사용자가 지정된 장치에서 동시에 20개의 응용 프로그램 공유 세션에 참가할 수 있습니다. 대부분의 사용자에게는 해당 값이면 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="f0078-p108">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients. This, too is recommended, but is not a hard-and-fast rule. In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range that means that the computer in question could participate in, at most, 100 communication sessions at any given time. Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients. Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time. That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="f0078-147">위의 포트 범위를 회의 구성 설정의 전역 컬렉션에 할당 하려면 다음 Lync Server 관리 셸 명령을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0078-147">To assign the preceding port ranges to your global collection of conferencing configuration settings you can use the following Lync Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="f0078-148">또는 다음 명령을 사용하여 모든 회의 구성 설정에 대해 동일한 포트 범위를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="f0078-148">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="f0078-149">개별 사용자는 Lync에서 로그 오프 한 다음 변경 내용을 실제로 적용 하기 전에 다시 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0078-149">Individual users must log off from Lync and then log back on before these changes will actually take effect.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f0078-150">명령 하나를 사용하여 클라이언트 미디어 포트 범위를 사용하도록 설정한 다음 해당 포트 범위를 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0078-150">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="f0078-151">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f0078-151">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

