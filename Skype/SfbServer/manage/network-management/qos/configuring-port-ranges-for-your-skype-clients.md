---
title: 클라이언트에 대한 포트 범위 및 서비스 품질 정책 구성
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 이 문서에서는 클라이언트에 대한 포트 범위를 구성하고 Windows 10에서 실행되는 클라이언트에 대해 비즈니스용 Skype 서버에서 서비스 품질 정책을 구성하는 방법을 설명합니다.
ms.openlocfilehash: b2961193bef799742ac3b79a4f421a7aa50c5a03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814208"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="36f96-103">비즈니스용 Skype 서버에서 클라이언트에 대한 포트 범위 및 서비스 품질 정책 구성</span><span class="sxs-lookup"><span data-stu-id="36f96-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="36f96-104">이 문서에서는 클라이언트에 대한 포트 범위를 구성하고 Windows 10에서 실행되는 클라이언트에 대해 비즈니스용 Skype 서버에서 서비스 품질 정책을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="36f96-105">포트 범위 구성</span><span class="sxs-lookup"><span data-stu-id="36f96-105">Configure port ranges</span></span>

<span data-ttu-id="36f96-106">기본적으로 비즈니스용 Skype 클라이언트 응용 프로그램은 통신 세션에 관련된 경우 포트 1024와 65535 사이의 모든 포트를 사용할 수 있습니다. 특정 포트 범위가 클라이언트에 대해 자동으로 사용하도록 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="36f96-107">그러나 서비스 품질을 사용하려면 다양한 트래픽 유형(오디오, 비디오, 미디어, 응용 프로그램 공유 및 파일 전송)을 일련의 고유한 포트 범위에 다시 재할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="36f96-108">이 수행은 cmdlet을 사용하여 Set-CsConferencingConfiguration 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="36f96-109">최종 사용자는 이러한 변경을 직접 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="36f96-110">포트 변경은 관리자만 이 cmdlet을 사용하여 Set-CsConferencingConfiguration 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="36f96-111">비즈니스용 Skype 서버 관리 셸 내에서 다음 명령을 실행하여 현재 통신 세션에 사용되는 포트 범위를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="36f96-112">비즈니스용 Skype 서버를 설치한 후 회의 설정을 변경하지 않은 경우 다음 속성 값을 포함하는 정보를 다시 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="36f96-113">위의 출력을 자세히 보면 두 가지 중요한 사항을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="36f96-114">먼저, ClientMediaPortRangeEnabled 속성이 False로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="36f96-115">이 속성을 False로 설정하면 비즈니스용 Skype 클라이언트가 통신 세션에 관련된 경우 포트 1024와 65535 사이의 사용 가능한 포트를 사용하기 때문에 중요합니다. 이는 다른 포트 설정(예: ClientMediaPort 또는 ClientVideoPort)에 관계없이 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="36f96-116">지정된 포트 집합으로 사용을 제한하려는 경우(그리고 서비스 품질 구현을 계획하는 경우 이 작업을 원하는 경우) 먼저 클라이언트 미디어 포트 범위를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="36f96-117">이 명령은 다음 명령으로 Windows PowerShell 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="36f96-p105">위의 명령은 회의 구성 설정의 전역 컬렉션에 대해 클라이언트 미디어 포트 범위를 사용하도록 설정합니다. 그러나 이러한 설정은 사이트 범위 및/또는 서비스 범위(회의 서버 서비스에 한함)에도 적용할 수 있습니다. 특정 사이트 또는 서버에 대해 클라이언트 미디어 포트 범위를 사용하도록 설정하려면 Set-CsConferencingConfiguration을 호출할 때 해당 사이트 또는 서버의 Identity를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-p105">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only). To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="36f96-120">또는 이 명령을 사용하여 모든 회의 구성 설정에 대해 포트 범위를 동시에 사용하도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="36f96-121">위의 출력에서 두 번째로 중요한 사항은 예제 출력에서 기본적으로 각 네트워크 트래픽 유형에 대해 설정된 미디어 포트 범위가 동일하다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="36f96-p106">QoS를 구현하려면 이러한 각 포트 범위가 고유해야 합니다. 예를 들어 포트 범위를 다음과 같이 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-p106">In order to implement QoS, each of these port ranges will need to be unique. For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36f96-124">클라이언트 트래픽 유형</span><span class="sxs-lookup"><span data-stu-id="36f96-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="36f96-125">포트 시작</span><span class="sxs-lookup"><span data-stu-id="36f96-125">Port Start</span></span></th>
<th><span data-ttu-id="36f96-126">포트 범위</span><span class="sxs-lookup"><span data-stu-id="36f96-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36f96-127">오디오</span><span class="sxs-lookup"><span data-stu-id="36f96-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="36f96-128">50020</span><span class="sxs-lookup"><span data-stu-id="36f96-128">50020</span></span></p></td>
<td><p><span data-ttu-id="36f96-129">20</span><span class="sxs-lookup"><span data-stu-id="36f96-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36f96-130">비디오</span><span class="sxs-lookup"><span data-stu-id="36f96-130">Video</span></span></p></td>
<td><p><span data-ttu-id="36f96-131">58000</span><span class="sxs-lookup"><span data-stu-id="36f96-131">58000</span></span></p></td>
<td><p><span data-ttu-id="36f96-132">20</span><span class="sxs-lookup"><span data-stu-id="36f96-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36f96-133">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="36f96-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="36f96-134">42000</span><span class="sxs-lookup"><span data-stu-id="36f96-134">42000</span></span></p></td>
<td><p><span data-ttu-id="36f96-135">20</span><span class="sxs-lookup"><span data-stu-id="36f96-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36f96-136">파일 전송</span><span class="sxs-lookup"><span data-stu-id="36f96-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="36f96-137">42020</span><span class="sxs-lookup"><span data-stu-id="36f96-137">42020</span></span></p></td>
<td><p><span data-ttu-id="36f96-138">20</span><span class="sxs-lookup"><span data-stu-id="36f96-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="36f96-139">위의 표에서 클라이언트 포트 범위는 서버에 대해 구성된 포트 범위의 하위 집합을 나타내고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="36f96-140">예를 들어 서버에서 응용 프로그램 공유는 포트 40803 ~ 49151을 사용하도록 구성했습니다. 클라이언트 컴퓨터에서 응용 프로그램 공유는 포트 42000~42019를 사용하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="36f96-141">클라이언트 포트가 서버에서 사용되는 포트의 하위 집합을 나타내지 않는 등 QoS를 보다 쉽게 관리하기 위해 이 작업을 주로 수행하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="36f96-142">예를 들어 클라이언트 컴퓨터에서는 포트 10000에서 10019까지 사용하도록 응용 프로그램 공유를 구성할 수 있습니다. 그러나 클라이언트 포트 범위를 서버 포트 범위의 하위 집합으로 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="36f96-143">또한 서버에서 응용 프로그램 공유를 위해 8348개 포트가 설정되어 있지만 클라이언트에서 응용 프로그램 공유를 위해 20개 포트만 설정되어 있는 것으로 나타났습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="36f96-144">이 규칙도 권장되지만 하드 및 빠른 규칙은 아니어도 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="36f96-145">일반적으로 사용 가능한 각 포트를 단일 통신 세션을 나타내는 것으로 고려할 수 있습니다. 포트 범위에서 100개 포트를 사용할 수 있는 경우 해당 컴퓨터가 특정 시기에 통신 세션을 100개까지 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="36f96-146">서버는 클라이언트보다 훨씬 많은 대화에 참여할 가능성이 높기 때문에 클라이언트보다 서버에서 더 많은 포트를 여는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="36f96-147">클라이언트에서 응용 프로그램 공유를 위해 20개 포트를 설정하면 사용자가 지정된 장치에서 20개 응용 프로그램 공유 세션에 동시에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="36f96-148">이는 대부분의 사용자에게 충분히 증명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="36f96-149">위의 포트 범위를 회의 구성 설정의 전역 컬렉션에 할당하려면 다음 비즈니스용 Skype 서버 관리 셸 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="36f96-150">또는 다음 명령을 사용하여 모든 회의 구성 설정에 대해 동일한 포트 범위를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="36f96-151">개별 사용자는 비즈니스용 Skype에서 로그오프한 다음 다시 로그온해야 이러한 변경 내용이 실제로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="36f96-152">명령 하나를 사용하여 클라이언트 미디어 포트 범위를 사용하도록 설정한 다음 해당 포트 범위를 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="36f96-153">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="36f96-154">Windows 10에서 실행되는 클라이언트에 대한 서비스 품질 정책 구성</span><span class="sxs-lookup"><span data-stu-id="36f96-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="36f96-155">비즈니스용 Skype 클라이언트에서 사용할 포트 범위를 지정할 뿐만 아니라 클라이언트 컴퓨터에 적용되는 별도의 서비스 품질 정책도 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="36f96-156">회의, 응용 프로그램 및 중재 서버에 대해 만들어진 서비스 품질 정책을 클라이언트 컴퓨터에 적용하면 안 됩니다. 이 정보는 비즈니스용 Skype 클라이언트 및 Windows 10을 실행하는 컴퓨터에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="36f96-157">다음 예에서는 이 포트 범위 집합을 사용하여 오디오 정책 및 비디오 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36f96-158">클라이언트 트래픽 유형</span><span class="sxs-lookup"><span data-stu-id="36f96-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="36f96-159">포트 시작</span><span class="sxs-lookup"><span data-stu-id="36f96-159">Port Start</span></span></th>
<th><span data-ttu-id="36f96-160">포트 범위</span><span class="sxs-lookup"><span data-stu-id="36f96-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36f96-161">오디오</span><span class="sxs-lookup"><span data-stu-id="36f96-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="36f96-162">50020</span><span class="sxs-lookup"><span data-stu-id="36f96-162">50020</span></span></p></td>
<td><p><span data-ttu-id="36f96-163">20</span><span class="sxs-lookup"><span data-stu-id="36f96-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36f96-164">비디오</span><span class="sxs-lookup"><span data-stu-id="36f96-164">Video</span></span></p></td>
<td><p><span data-ttu-id="36f96-165">58000</span><span class="sxs-lookup"><span data-stu-id="36f96-165">58000</span></span></p></td>
<td><p><span data-ttu-id="36f96-166">20</span><span class="sxs-lookup"><span data-stu-id="36f96-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36f96-167">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="36f96-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="36f96-168">42000</span><span class="sxs-lookup"><span data-stu-id="36f96-168">42000</span></span></p></td>
<td><p><span data-ttu-id="36f96-169">20</span><span class="sxs-lookup"><span data-stu-id="36f96-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36f96-170">파일 전송</span><span class="sxs-lookup"><span data-stu-id="36f96-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="36f96-171">42020</span><span class="sxs-lookup"><span data-stu-id="36f96-171">42020</span></span></p></td>
<td><p><span data-ttu-id="36f96-172">20</span><span class="sxs-lookup"><span data-stu-id="36f96-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="36f96-173">Windows 10 컴퓨터에 대한 서비스 품질 오디오 정책을 만들하려면 먼저 그룹 정책 관리가 설치된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="36f96-174">그룹 정책 관리를 열고(시작, 관리 도구를 클릭한 다음 그룹 정책 관리를 클릭) 다음 절차를 완료합니다.  </span><span class="sxs-lookup"><span data-stu-id="36f96-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="36f96-175">그룹 정책 관리에서 새 정책을 만들 컨테이너를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="36f96-176">예를 들어 모든 클라이언트 컴퓨터가 Clients라는 OU에 있는 경우 클라이언트 OU에서 새 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="36f96-177">적절한 컨테이너를 마우스 오른쪽 단추로 클릭한 다음 이 도메인에서 GPO 만들기를 클릭하고 여기에 **연결합니다.**</span><span class="sxs-lookup"><span data-stu-id="36f96-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="36f96-178">새 **GPO** 대화 상자의 이름 상자에 새 그룹  정책 개체의 이름을 입력하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="36f96-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="36f96-179">새로 만든 정책을 마우스 오른쪽 단추로 클릭한 다음 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="36f96-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="36f96-180">그룹 정책 관리 편집기에서 컴퓨터 **구성을** **확장하고, Windows 설정을** 확장하고, 정책 기반 **QoS를** 마우스 오른쪽 단추로 클릭한 다음 새 정책 **만들기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="36f96-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="36f96-181">정책 기반 **QoS** 대화 상자의 열기 페이지에서 이름 상자에 새 정책의 이름을 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="36f96-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="36f96-182">**DSCP 값 지정** 을 선택하고 값을 **46** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="36f96-183">**아웃바운드 스로틀 속도 지정** 은 선택되지 않은 상태로 두고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="36f96-184">다음 페이지에서 이 실행 가능한 이름이 있는 응용  프로그램만 선택하고Lync.exe이름으로 입력한 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="36f96-184">On the next page, select **Only applications with this executable name**, enter **Lync.exe** as the name, and then click **Next**.</span></span> <span data-ttu-id="36f96-185">이 설정은 비즈니스용 Skype 클라이언트에서 일치하는 트래픽의 우선 순위를 지정하는 정책에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-185">This setting instructs the policy to only prioritize matching traffic from the Skype for Business client.</span></span>

8.  <span data-ttu-id="36f96-186">세 번째 페이지에서 원본 **IP** 주소와 모든 대상 **IP** 주소가 모두 선택되어 있는지 확인한 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="36f96-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="36f96-187">이러한 두 설정은 해당 패킷을 전송하는 컴퓨터(IP 주소) 및 패킷을 수신하는 컴퓨터(IP 주소)에 관계없이 패킷이 관리되도록 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="36f96-188">4페이지에서는 **이 QoS 정책이 적용되는 프로토콜 선택** 드롭다운 목록에서 **TCP 및 UDP** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="36f96-189">TCP(Transmission Control Protocol) 및 UDP(User Datagram Protocol)는 비즈니스용 Skype 서버 및 해당 클라이언트 응용 프로그램에서 가장 일반적으로 사용되는 두 가지 네트워킹 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="36f96-190">**원본 포트 번호 지정** 제목 아래에서 **이 원본 포트 또는 범위부터** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-190">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="36f96-191">포함된 텍스트 상자에는 오디오 전송에 예약된 포트 범위를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-191">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="36f96-192">예를 들어 오디오 트래픽에 대해 포트 50020~50039를 예약한 경우 다음 형식을 사용하여 포트 범위를 입력합니다. **50020:50039**.</span><span class="sxs-lookup"><span data-stu-id="36f96-192">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="36f96-193">**마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-193">Click **Finish**.</span></span>

<span data-ttu-id="36f96-194">오디오에 대한 QoS 정책을 만든 후 비디오에 대한 두 번째 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-194">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="36f96-195">비디오용 정책을 만들려면 오디오 정책을 만들 때 수행한 것과 기본적으로는 같은 절차를 따르되 다음 항목을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-195">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="36f96-196">다른(고유한) 정책 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="36f96-197">DSCP 값을 46이 아닌 **34** 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-197">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="36f96-198">앞서 언급했듯이 DSCP 값 34를 사용할 것은 아니며 오디오에 사용되는 DSCP 값과 다른 DSCP 값을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-198">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="36f96-199">비디오 트래픽에 대해 이전에 구성된 포트 범위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="36f96-200">예를 들어 비디오용 포트 58000에서 58019를 예약한 경우 포트 범위를 **58000:58019로** 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="36f96-201">응용 프로그램 공유 트래픽을 관리하기 위한 정책을 만들 경우 다음을 다음으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="36f96-202">다른 고유한 정책 이름(예: 비즈니스용 Skype 서버 응용 프로그램 **공유)을 사용하세요.**</span><span class="sxs-lookup"><span data-stu-id="36f96-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="36f96-203">DSCP 값을 46이 아닌 **24** 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-203">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="36f96-204">다시 말해서 이 값은 24가 아니어도 됩니다. 오디오 및 비디오에 사용되는 DSCP 값과 달라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-204">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="36f96-205">비디오 트래픽에 대해 이전에 구성된 포트 범위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="36f96-206">예를 들어 응용 프로그램 공유를 위해 포트 42000~42019를 예약한 경우 포트 범위를 **42000:42019로** 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="36f96-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="36f96-207">파일 전송 정책의 경우:</span><span class="sxs-lookup"><span data-stu-id="36f96-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="36f96-208">다른 고유한 정책 이름(예: **비즈니스용 Skype 서버 파일 전송)을 사용하세요.**</span><span class="sxs-lookup"><span data-stu-id="36f96-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="36f96-209">DSCP 값을 **14로 설정**</span><span class="sxs-lookup"><span data-stu-id="36f96-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="36f96-210">(다시 말해서 이 값은 14가 아니어도 됩니다. 단순히 고유한 DSCP 코드일 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="36f96-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="36f96-211">응용 프로그램에 대해 이전에 구성된 포트 범위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="36f96-212">예를 들어 응용 프로그램 공유를 위해 포트 42020~42039를 예약한 경우 포트 범위를 **42020:42039로** 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="36f96-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="36f96-213">만든 새 정책은 클라이언트 컴퓨터에서 그룹 정책을 새로 고칠 때까지 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-213">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="36f96-214">그룹 정책은 일정한 간격에 따라 자체적으로 새로 고쳐지기는 하지만, 그룹 정책을 새로 고쳐야 하는 각 컴퓨터에서 다음 명령을 실행하면 그룹 정책을 강제로 즉시 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-214">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="36f96-215">이 명령은 관리자 자격 증명으로 실행되는 모든 명령 창에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-215">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="36f96-216">관리자 자격 증명을 사용한 명령 창을 실행하려면 **시작** 을 클릭하고 **명령 프롬프트** 를 마우스 오른쪽 단추로 클릭한 후 **관리자 권한으로 실행** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-216">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="36f96-217">이러한 정책은 클라이언트 컴퓨터를 대상으로 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="36f96-218">이러한 서버는 비즈니스용 Skype 서버를 실행하는 서버에 적용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="36f96-219">네트워크 패킷이 적절한 DSCP 값으로 표시되도록 하려면 다음 절차를 완료하여 각 컴퓨터에서 새 레지스트리 항목도 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="36f96-220">**시작** 을 클릭한 다음 **실행** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="36f96-221">실행 **대화 상자에서** **regedit를** 입력한 다음 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="36f96-222">레지스트리 편집기에서 **HKEY \_ LOCAL \_ MACHINE,** **SYSTEM,** **CurrentControlSet,** 서비스 및 **Tcpip를** 확장합니다. </span><span class="sxs-lookup"><span data-stu-id="36f96-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="36f96-223">**Tcpip** 를 마우스 오른쪽 단추로 클릭하고 **새로 만들기** 를 가리킨 다음 **키** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="36f96-224">새 레지스트리 키를 만든 후 **QoS를** 입력한 다음 Enter 키를 눌러 키 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="36f96-225">**QoS** 를 마우스 오른쪽 단추로 클릭하고 **새로 만들기** 를 가리킨 다음 **문자열 값** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="36f96-226">새 레지스트리 값을 만든 후 **NLA를** 사용하지 말고 Enter를 눌러 값 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="36f96-227">NLA 사용 안 를 두 **번 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="36f96-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="36f96-228">문자열 **편집** 대화 상자에서 값 데이터  **상자에 1을** 입력하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="36f96-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="36f96-229">레지스트리 편집기를 닫고 컴퓨터를 eboot합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="36f96-230">여러 네트워크 어댑터가 있는 컴퓨터에서 서비스 품질 구성</span><span class="sxs-lookup"><span data-stu-id="36f96-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="36f96-231">여러 개의 네트워크 어댑터가 있는 컴퓨터가 있는 경우 DSCP 값이 구성된 값 대신 0x00 표시되는 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="36f96-232">일반적으로 하나 이상의 네트워크 어댑터가 Active Directory 도메인에 액세스할 수 없는 컴퓨터에서 발생합니다(예: 이러한 어댑터가 개인 네트워크에 사용되는 경우).</span><span class="sxs-lookup"><span data-stu-id="36f96-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="36f96-233">이러한 경우 DSCP 값은 도메인에 액세스할 수 있는 어댑터에 대해 태그가 지정되지만 도메인에 액세스할 수 없는 어댑터에는 태그가 지정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="36f96-234">도메인에 액세스할 수 없는 어댑터를 포함하여 컴퓨터의 모든 네트워크 어댑터에 대한 DSCP 값에 태그를 지정하려면 레지스트리에 값을 추가하고 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="36f96-235">이 작업은 다음 절차에 따라 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="36f96-236">**시작** 을 클릭한 다음 **실행** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="36f96-237">실행 **대화 상자에서** **regedit를** 입력한 다음 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="36f96-238">레지스트리 편집기에서 **HKEY \_ LOCAL \_ MACHINE,** **SYSTEM,** **CurrentControlSet,** 서비스 및 **Tcpip를** 확장합니다. </span><span class="sxs-lookup"><span data-stu-id="36f96-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="36f96-239">**QoS에** 레이블이 붙은 레지스트리 키가 없는 경우 **Tcpip을** 마우스 오른쪽 단추로 클릭하고 새로 고를 클릭한 다음 **키를 클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="36f96-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="36f96-240">새 키를 만든 후 **QoS를** 입력한 다음 Enter 키를 눌러 키 이름을 이름을 입니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="36f96-241">**QoS** 를 마우스 오른쪽 단추로 클릭하고 **새로 만들기** 를 가리킨 다음 **문자열 값** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="36f96-242">새 레지스트리 값을 만든 후 **NLA를** 사용하지 말고 Enter를 눌러 값 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="36f96-243">NLA 사용 안 를 두 **번 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="36f96-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="36f96-244">문자열 **편집** 대화 상자에서 값 데이터  **상자에 1을** 입력하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="36f96-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="36f96-245">새 레지스트리 값을 만들고 구성한 후 변경 내용을 적용하려면 컴퓨터를 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36f96-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="36f96-246">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36f96-246">See also</span></span>

[<span data-ttu-id="36f96-247">Windows 10에서 그룹 정책 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="36f96-247">Create a Group Policy Object in Windows 10</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
