---
title: 클라이언트의 포트 범위 및 서비스 품질 정책 구성
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 이 문서에서는 Windows 10에서 실행 되는 클라이언트의 비즈니스용 Skype 서버에서 클라이언트의 포트 범위를 구성 하 고 서비스 품질 정책을 구성 하는 방법을 설명 합니다.
ms.openlocfilehash: 9a82a254ab5a01982e9f1d4bd3a994fd67c03615
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817427"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="f3d72-103">비즈니스용 Skype 서버에서 클라이언트에 대 한 포트 범위 및 서비스 품질 정책 구성</span><span class="sxs-lookup"><span data-stu-id="f3d72-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="f3d72-104">이 문서에서는 Windows 10에서 실행 되는 클라이언트의 비즈니스용 Skype 서버에서 클라이언트의 포트 범위를 구성 하 고 서비스 품질 정책을 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="f3d72-105">포트 범위 구성</span><span class="sxs-lookup"><span data-stu-id="f3d72-105">Configure port ranges</span></span>

<span data-ttu-id="f3d72-106">기본적으로 비즈니스용 Skype 클라이언트 응용 프로그램은 통신 세션에 관여 했을 때 포트 1024 및 65535 간의 모든 포트를 사용할 수 있습니다. 이는 특정 포트 범위가 클라이언트에 대해 자동으로 사용 되지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="f3d72-107">그러나 서비스 품질을 사용 하기 위해서는 다양 한 트래픽 형식 (오디오, 비디오, 미디어, 응용 프로그램 공유 및 파일 전송)을 일련의 고유한 포트 범위에 다시 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="f3d72-108">Set-CsConferencingConfiguration cmdlet을 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="f3d72-109">최종 사용자는 이러한 변경을 자체적으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="f3d72-110">포트 변경은 Set-CsConferencingConfiguration cmdlet을 사용 하는 관리자만 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="f3d72-111">비즈니스용 Skype 서버 관리 셸에서 다음 명령을 실행 하 여 현재 통신 세션에 사용 되는 포트 범위를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="f3d72-112">비즈니스용 Skype 서버를 설치한 후 회의 설정을 변경 하지 않은 경우에는 다음 속성 값이 포함 된 정보를 다시 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="f3d72-113">앞의 출력을 자세히 살펴보면 두 가지 중요성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="f3d72-114">먼저 ClientMediaPortRangeEnabled 속성이 False로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="f3d72-115">이 속성을 False로 설정 하면 비즈니스용 Skype 클라이언트는 통신 세션에 참여할 때 포트 1024 및 65535 사이에 사용 가능한 포트를 사용 하기 때문에 중요 합니다. 이는 다른 포트 설정 (예: ClientMediaPort 또는 ClientVideoPort)에 관계 없이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="f3d72-116">지정 된 포트 집합으로 사용을 제한 하려는 경우 (서비스 품질을 구현 하는 데 필요한 경우) 먼저 클라이언트 미디어 포트 범위를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="f3d72-117">다음 Windows PowerShell 명령을 사용 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="f3d72-118">앞의 명령을 사용 하면 회의 구성 설정의 전역 컬렉션에 대 한 클라이언트 미디어 포트 범위가 설정 됩니다. 그러나 이러한 설정은 사이트 범위 및/또는 서비스 범위 (회의 서버 서비스의 경우)에도 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-118">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only).</span></span> <span data-ttu-id="f3d72-119">특정 사이트 또는 서버에 대해 클라이언트 미디어 포트 범위를 사용 하도록 설정 하려면 Set-CsConferencingConfiguration를 호출할 때 해당 사이트 또는 서버의 Id를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-119">To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="f3d72-120">또는이 명령을 사용 하 여 모든 회의 구성 설정에 대해 포트 범위를 동시에 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="f3d72-121">중요 한 두 번째 작업은 기본적으로 각 네트워크 트래픽 유형에 대해 설정 된 미디어 포트 범위가 동일 하다는 것을 보여 주는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="f3d72-122">QoS를 구현 하기 위해 이러한 각 포트 범위는 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-122">In order to implement QoS, each of these port ranges will need to be unique.</span></span> <span data-ttu-id="f3d72-123">예를 들어 다음과 같이 포트 범위를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-123">For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f3d72-124">클라이언트 트래픽 형식</span><span class="sxs-lookup"><span data-stu-id="f3d72-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="f3d72-125">포트 시작</span><span class="sxs-lookup"><span data-stu-id="f3d72-125">Port Start</span></span></th>
<th><span data-ttu-id="f3d72-126">포트 범위</span><span class="sxs-lookup"><span data-stu-id="f3d72-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3d72-127">오디오</span><span class="sxs-lookup"><span data-stu-id="f3d72-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="f3d72-128">50020</span><span class="sxs-lookup"><span data-stu-id="f3d72-128">50020</span></span></p></td>
<td><p><span data-ttu-id="f3d72-129">명</span><span class="sxs-lookup"><span data-stu-id="f3d72-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3d72-130">비디오만</span><span class="sxs-lookup"><span data-stu-id="f3d72-130">Video</span></span></p></td>
<td><p><span data-ttu-id="f3d72-131">58000</span><span class="sxs-lookup"><span data-stu-id="f3d72-131">58000</span></span></p></td>
<td><p><span data-ttu-id="f3d72-132">명</span><span class="sxs-lookup"><span data-stu-id="f3d72-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3d72-133">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="f3d72-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="f3d72-134">42000</span><span class="sxs-lookup"><span data-stu-id="f3d72-134">42000</span></span></p></td>
<td><p><span data-ttu-id="f3d72-135">명</span><span class="sxs-lookup"><span data-stu-id="f3d72-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3d72-136">파일 전송</span><span class="sxs-lookup"><span data-stu-id="f3d72-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="f3d72-137">42020</span><span class="sxs-lookup"><span data-stu-id="f3d72-137">42020</span></span></p></td>
<td><p><span data-ttu-id="f3d72-138">명</span><span class="sxs-lookup"><span data-stu-id="f3d72-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f3d72-139">위의 표에서 클라이언트 포트 범위는 서버에 대해 구성 된 포트 범위의 하위 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="f3d72-140">예를 들어 서버에서 응용 프로그램 공유가 포트 40803 ~ 49151을 사용 하도록 구성 되었습니다. 클라이언트 컴퓨터에서 응용 프로그램 공유는 포트 42000 ~ 42019을 사용 하도록 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="f3d72-141">이를 통해 QoS를 더욱 쉽게 관리할 수 있습니다. 클라이언트 포트는 서버에 사용 되는 포트의 하위 집합을 나타낼 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="f3d72-142">(예를 들어, 클라이언트 컴퓨터에서 응용 프로그램 공유를 구성 하는 데 사용할 수 있는 포트 1만 ~ 10019을 말합니다.) 그러나 클라이언트 포트 범위를 서버 포트 범위의 하위 집합으로 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="f3d72-143">또한, 서버에 대 한 응용 프로그램 공유에 대 한 8348 포트가 별도로 설정 되었지만 클라이언트의 응용 프로그램 공유에 대해 20 개의 포트만 따로 설정 되었다는 사실을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="f3d72-144">이 역시 좋은 방법 이지만,이는 어려운 규칙이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="f3d72-145">일반적으로 하나의 통신 세션을 나타내기 위해 사용 가능한 각 포트를 고려할 수 있습니다. 따라서 포트 범위에서 100 포트를 사용할 수 있는 경우 해당 컴퓨터가 주어진 시간에 최대 100의 통신 세션에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="f3d72-146">서버는 클라이언트 보다 많은 대화에 참여 하기 때문에 클라이언트 보다 더 많은 포트를 서버에서 여는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="f3d72-147">클라이언트에서 응용 프로그램을 공유 하기 위해 20 포트를 별도로 설정 하면 사용자가 지정 된 디바이스의 20 개 응용 프로그램 공유 세션에 동시에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="f3d72-148">이는 대부분의 사용자에 게 충분 한지 입증 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="f3d72-149">앞의 포트 범위를 회의 구성 설정의 전역 컬렉션에 할당 하려면 다음 비즈니스용 Skype Server 관리 셸 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="f3d72-150">또는이 명령을 사용 하 여 모든 회의 구성 설정에 대해 동일한 포트 범위를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="f3d72-151">개별 사용자는 비즈니스용 Skype에서 로그 오프 한 다음 다시 로그인 해야 변경 내용이 실제로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="f3d72-152">또한 클라이언트 미디어 포트 범위를 사용 하도록 설정한 다음 단일 명령을 사용 하 여 해당 포트 범위를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="f3d72-153">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="f3d72-154">Windows 10에서 실행 되는 클라이언트에 대 한 서비스 품질 정책 구성</span><span class="sxs-lookup"><span data-stu-id="f3d72-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="f3d72-155">비즈니스용 Skype 클라이언트에서 사용할 포트 범위를 지정 하는 것 외에도 클라이언트 컴퓨터에 적용 되는 별도의 서비스 품질 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="f3d72-156">(회의, 응용 프로그램 및 중재 서버에 대해 생성 되는 서비스 품질 정책은 클라이언트 컴퓨터에 적용 되어서는 안 됩니다.) 이 정보는 비즈니스용 Skype 클라이언트 및 Windows 10을 실행 하는 컴퓨터에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="f3d72-157">다음 예에서는이 포트 범위 집합을 사용 하 여 오디오 정책 및 비디오 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f3d72-158">클라이언트 트래픽 형식</span><span class="sxs-lookup"><span data-stu-id="f3d72-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="f3d72-159">포트 시작</span><span class="sxs-lookup"><span data-stu-id="f3d72-159">Port Start</span></span></th>
<th><span data-ttu-id="f3d72-160">포트 범위</span><span class="sxs-lookup"><span data-stu-id="f3d72-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3d72-161">오디오</span><span class="sxs-lookup"><span data-stu-id="f3d72-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="f3d72-162">50020</span><span class="sxs-lookup"><span data-stu-id="f3d72-162">50020</span></span></p></td>
<td><p><span data-ttu-id="f3d72-163">명</span><span class="sxs-lookup"><span data-stu-id="f3d72-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3d72-164">비디오만</span><span class="sxs-lookup"><span data-stu-id="f3d72-164">Video</span></span></p></td>
<td><p><span data-ttu-id="f3d72-165">58000</span><span class="sxs-lookup"><span data-stu-id="f3d72-165">58000</span></span></p></td>
<td><p><span data-ttu-id="f3d72-166">명</span><span class="sxs-lookup"><span data-stu-id="f3d72-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3d72-167">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="f3d72-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="f3d72-168">42000</span><span class="sxs-lookup"><span data-stu-id="f3d72-168">42000</span></span></p></td>
<td><p><span data-ttu-id="f3d72-169">명</span><span class="sxs-lookup"><span data-stu-id="f3d72-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3d72-170">파일 전송</span><span class="sxs-lookup"><span data-stu-id="f3d72-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="f3d72-171">42020</span><span class="sxs-lookup"><span data-stu-id="f3d72-171">42020</span></span></p></td>
<td><p><span data-ttu-id="f3d72-172">명</span><span class="sxs-lookup"><span data-stu-id="f3d72-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f3d72-173">Windows 10 컴퓨터용 서비스 품질 오디오 정책을 만들려면 먼저 그룹 정책 관리가 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="f3d72-174">그룹 정책 관리 ( **시작**을 클릭 하 고 **관리 도구**를 가리킨 다음 **그룹 정책 관리**클릭)를 열고 다음 절차를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="f3d72-175">그룹 정책 관리에서 새 정책을 만들 컨테이너를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="f3d72-176">예를 들어 모든 클라이언트 컴퓨터가 클라이언트 라는 OU에 있는 경우 클라이언트 OU에서 새 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="f3d72-177">적절 한 컨테이너를 마우스 오른쪽 단추로 클릭 한 다음 **이 도메인에서 GPO 만들기를 클릭 하 고 여기에 연결**합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="f3d72-178">**새 GPO** 대화 상자의 **이름** 상자에 새 그룹 정책 개체의 이름을 입력 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="f3d72-179">새로 만든 정책을 마우스 오른쪽 단추로 클릭 한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="f3d72-180">그룹 정책 관리 편집기에서 **컴퓨터 구성**, **Windows 설정을**차례로 확장 하 고 **정책 기반 QoS**를 마우스 오른쪽 단추로 클릭 한 다음 **새 정책 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="f3d72-181">**정책 기반 QoS** 대화 상자의 열기 페이지에 있는 **이름** 상자에 새 정책의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="f3d72-182">**DSCP 값 지정** 을 선택 하 고 값을 **46**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="f3d72-183">**아웃 바운드 스로틀 속도 지정** 을 선택 하지 않은 상태로 두고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="f3d72-184">다음 페이지에서 **이 실행 파일 이름의 응용**프로그램만 선택 하 고 **다음**을 클릭 하 여 해당 **이름을 입력 하** 고</span><span class="sxs-lookup"><span data-stu-id="f3d72-184">On the next page, select **Only applications with this executable name**, enter **Lync.exe** as the name, and then click **Next**.</span></span> <span data-ttu-id="f3d72-185">이 설정은 비즈니스용 Skype 클라이언트에서 일치 하는 소통에 대 한 우선 순위만 지정 하도록 정책에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-185">This setting instructs the policy to only prioritize matching traffic from the Skype for Business client.</span></span>

8.  <span data-ttu-id="f3d72-186">세 번째 페이지에서 **원본 ip 주소** 와 **대상 ip 주소가** 모두 선택 되어 있는지 확인 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="f3d72-187">이러한 두 가지 설정은 해당 패킷과 전송 되는 컴퓨터 (ip 주소) 및 해당 패킷을 받을 컴퓨터 (IP 주소)에 관계 없이 패킷이 관리 됨을 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="f3d72-188">4 페이지에서 **이 QoS 정책이 적용 되는 프로토콜 선택** 드롭다운 목록에서 **TCP 및 UDP** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="f3d72-189">TCP (전송 제어 프로토콜) 및 UDP (사용자 데이터 그램 프로토콜)는 비즈니스용 Skype Server 및 해당 클라이언트 응용 프로그램에서 가장 일반적으로 사용 되는 두 가지 네트워킹 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="f3d72-190">**원본 포트 번호를 지정 하는**제목 아래에서 **이 원본 포트 또는 범위를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-190">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="f3d72-191">해당 텍스트 상자에 오디오 전송용으로 예약 된 포트 범위를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-191">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="f3d72-192">예를 들어 오디오 트래픽에 포트 50039을 통해 포트 50020를 예약한 경우이 형식을 사용 하 여 포트 범위를 입력 합니다 ( **50020:50039**).</span><span class="sxs-lookup"><span data-stu-id="f3d72-192">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="f3d72-193">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-193">Click **Finish**.</span></span>

<span data-ttu-id="f3d72-194">오디오에 대 한 QoS 정책을 만든 후에는 비디오에 대 한 두 번째 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-194">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="f3d72-195">비디오에 대 한 정책을 만들려면 오디오 정책을 만들 때 팔 로우 하는 기본 절차를 따르고 다음과 같이 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-195">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="f3d72-196">다른 (및 고유) 정책 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="f3d72-197">DSCP 값을 46 대신 **34** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-197">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="f3d72-198">(앞에서 설명한 것 처럼, DSCP 값 34을 사용할 필요가 없으며, 오디오에 사용 되는 것과 다른 DSCP 값을 할당 하기만 하면 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="f3d72-198">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="f3d72-199">이전에 구성한 비디오 트래픽에 대 한 포트 범위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="f3d72-200">예를 들어 비디오에 대 한 58019 58000를 예약한 포트를 사용 하는 경우 포트 범위를 this: **58000:58019**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="f3d72-201">응용 프로그램 공유 트래픽을 관리 하기 위한 정책을 만들려는 경우 다음과 같이 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="f3d72-202">다른 고유 정책 이름 (예: **비즈니스용 Skype 서버 응용 프로그램 공유**)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="f3d72-203">46 대신 DSCP 값을 **24** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-203">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="f3d72-204">(이 값은 24 일 필요는 없으며, 오디오 및 비디오에 사용 되는 DSCP 값과 달라 야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="f3d72-204">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="f3d72-205">이전에 구성한 비디오 트래픽에 대 한 포트 범위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="f3d72-206">예를 들어 응용 프로그램 공유에 대해 포트 42000 ~ 42019을 (를) 예약한 경우 포트 범위를 this: **42000:42019**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="f3d72-207">파일 전송 정책:</span><span class="sxs-lookup"><span data-stu-id="f3d72-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="f3d72-208">다른 (고유) 정책 이름 (예: **비즈니스용 Skype 서버 파일 전송**)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="f3d72-209">DSCP 값을 **14**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="f3d72-210">(이 값은 14 일 필요는 없으며 단순히 고유한 DSCP 코드 여야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="f3d72-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="f3d72-211">이전에 구성 된 응용 프로그램의 포트 범위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="f3d72-212">예를 들어 응용 프로그램 공유에 대해 포트 42020 ~ 42039을 (를) 예약한 경우 포트 범위를 this: **42020:42039**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="f3d72-213">만든 새 정책은 클라이언트 컴퓨터에서 그룹 정책을 새로 고칠 때까지 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-213">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="f3d72-214">그룹 정책은 주기적으로 자체적으로 새로 고쳐지고 그룹 정책을 새로 고쳐야 하는 각 컴퓨터에서 다음 명령을 실행 하 여 즉시 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-214">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="f3d72-215">이 명령은 관리자 자격 증명으로 실행 되는 모든 명령 창에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-215">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="f3d72-216">명령 창을 관리자 자격 증명으로 실행 하려면 **시작**을 클릭 하 고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-216">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="f3d72-217">이러한 정책은 클라이언트 컴퓨터를 대상으로 해야 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3d72-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="f3d72-218">비즈니스용 Skype Server를 실행 하는 서버에는 적용 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="f3d72-219">네트워크 패킷이 적절 한 DSCP 값으로 표시 되도록 하려면 다음 절차를 완료 하 여 각 컴퓨터에 새 레지스트리 항목을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="f3d72-220">**시작**을 클릭 한 다음 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="f3d72-221">**실행** 대화 상자에서 **regedit**를 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="f3d72-222">레지스트리 편집기에서 **\_HKEY\_LOCAL MACHINE**을 확장 하 고 **시스템**, **CurrentControlSet**를 차례로 확장 한 다음 **서비스**를 확장 한 다음 **Tcpip**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="f3d72-223">**Tcpip**를 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 가리킨 다음 **키**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="f3d72-224">새 레지스트리 키를 만들고 **QoS**를 입력 한 다음 enter 키를 눌러 키의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="f3d72-225">**QoS**를 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 가리킨 다음 **문자열 값**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="f3d72-226">새 레지스트리 값을 만든 후에는 **NLA를 사용 하지 않음을**입력 하 고 enter 키를 눌러 값의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="f3d72-227">**NLA를 사용 하지 않음을**두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="f3d72-228">**문자열 편집** 대화 상자의 **값 데이터** 상자에 **1** 을 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="f3d72-229">레지스트리 편집기를 닫고 컴퓨터를 eboot.</span><span class="sxs-lookup"><span data-stu-id="f3d72-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="f3d72-230">여러 네트워크 어댑터를 사용 하는 컴퓨터에서 서비스 품질 구성</span><span class="sxs-lookup"><span data-stu-id="f3d72-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="f3d72-231">네트워크 어댑터가 여러 개 있는 컴퓨터를 사용 하는 경우 DSCP 값이 구성 된 값이 아닌 0x00으로 표시 되는 문제를 종종 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="f3d72-232">이 문제는 일반적으로 하나 이상의 네트워크 어댑터가 Active Directory 도메인에 액세스할 수 없는 컴퓨터에서 발생 합니다 (예: 해당 어댑터가 개인 네트워크에 사용 되는 경우).</span><span class="sxs-lookup"><span data-stu-id="f3d72-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="f3d72-233">이와 같은 경우 DSCP 값에는 도메인에 액세스할 수 있는 어댑터에 대 한 태그가 지정 되지만 도메인에 액세스할 수 없는 어댑터에는 태그가 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="f3d72-234">도메인에 대 한 액세스 권한이 없는 어댑터를 포함 하 여 컴퓨터에 있는 모든 네트워크 어댑터에 대해 DSCP 값에 태그를 지정 하려면 레지스트리에 값을 추가 하 고 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="f3d72-235">다음 절차를 완료 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="f3d72-236">**시작**을 클릭 한 다음 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="f3d72-237">**실행** 대화 상자에서 **regedit**를 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="f3d72-238">레지스트리 편집기에서 **\_HKEY\_LOCAL MACHINE**을 확장 하 고 **시스템**, **CurrentControlSet**를 차례로 확장 한 다음 **서비스**를 확장 한 다음 **Tcpip**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="f3d72-239">**QoS** 라는 레지스트리 키가 표시 되지 않으면 **Tcpip**를 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 가리킨 다음 **키**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="f3d72-240">새 키를 만들고 **QoS**를 입력 한 다음 enter 키를 눌러 키의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="f3d72-241">**QoS**를 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 가리킨 다음 **문자열 값**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="f3d72-242">새 레지스트리 값을 만든 후에는 **NLA를 사용 하지 않음을**입력 하 고 enter 키를 눌러 값의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="f3d72-243">**NLA를 사용 하지 않음을**두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="f3d72-244">**문자열 편집** 대화 상자의 **값 데이터** 상자에 **1** 을 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="f3d72-245">새 레지스트리 값을 만들고 구성한 후에는 컴퓨터를 다시 부팅 해야 변경 내용이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3d72-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3d72-246">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f3d72-246">See also</span></span>

[<span data-ttu-id="f3d72-247">Windows 10에서 그룹 정책 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="f3d72-247">Create a Group Policy Object in Windows 10</span></span>](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
