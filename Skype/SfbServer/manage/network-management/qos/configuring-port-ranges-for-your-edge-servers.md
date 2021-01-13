---
title: 에지 서버에 대한 포트 범위 및 서비스 품질 구성
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
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
description: 이 문서에서는 에지 서버에 대한 포트 범위를 구성하는 방법과 A/V 에지 서버에 대한 서비스 품질 정책을 구성하는 방법에 대해 설명합니다.
ms.openlocfilehash: c88f784fe1956fa16b8464caa4f9f26e5c61005e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832908"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a><span data-ttu-id="91fa0-103">비즈니스용 Skype 서버에서 에지 서버에 대한 포트 범위 및 서비스 품질 정책 구성</span><span class="sxs-lookup"><span data-stu-id="91fa0-103">Configuring port ranges and a Quality of Service policy for your Edge Servers in Skype for Business Server</span></span>

<span data-ttu-id="91fa0-104">이 문서에서는 에지 서버에 대한 포트 범위를 구성하는 방법과 A/V 에지 서버에 대한 서비스 품질 정책을 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-104">This article describes how to configure port ranges for Edge Servers and how to configure a Quality of Service policy for your A/V Edge Servers.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="91fa0-105">포트 범위 구성</span><span class="sxs-lookup"><span data-stu-id="91fa0-105">Configure port ranges</span></span>

<span data-ttu-id="91fa0-106">에지 서버를 사용하면 오디오, 비디오 및 응용 프로그램 공유에 대해 별도의 포트 범위를 구성할 수 없습니다. 마찬가지로 에지 서버에 사용되는 포트 범위는 회의, 응용 프로그램 및 중재 서버에서 사용되는 포트 범위와 일치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-106">With Edge servers, you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="91fa0-107">예제를 계속 진행하기 전에 이 옵션이 있는 동안에는 포트 범위를 변경하지 않는 것이 좋습니다. 50000 포트 범위에서 이동하는 경우 일부 시나리오에 부정적인 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-107">Before we proceed with our example, it's important to stress that while this option exists, we recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="91fa0-108">예를 들어 다음 포트 범위를 사용하도록 회의, 응용 프로그램 및 중재 서버를 구성했다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-108">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91fa0-109">패킷 유형</span><span class="sxs-lookup"><span data-stu-id="91fa0-109">Packet Type</span></span></th>
<th><span data-ttu-id="91fa0-110">시작 포트</span><span class="sxs-lookup"><span data-stu-id="91fa0-110">Starting Port</span></span></th>
<th><span data-ttu-id="91fa0-111">예약된 포트 수</span><span class="sxs-lookup"><span data-stu-id="91fa0-111">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91fa0-112">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="91fa0-112">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="91fa0-113">40803</span><span class="sxs-lookup"><span data-stu-id="91fa0-113">40803</span></span></p></td>
<td><p><span data-ttu-id="91fa0-114">8348</span><span class="sxs-lookup"><span data-stu-id="91fa0-114">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91fa0-115">오디오</span><span class="sxs-lookup"><span data-stu-id="91fa0-115">Audio</span></span></p></td>
<td><p><span data-ttu-id="91fa0-116">49152</span><span class="sxs-lookup"><span data-stu-id="91fa0-116">49152</span></span></p></td>
<td><p><span data-ttu-id="91fa0-117">8348</span><span class="sxs-lookup"><span data-stu-id="91fa0-117">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91fa0-118">비디오</span><span class="sxs-lookup"><span data-stu-id="91fa0-118">Video</span></span></p></td>
<td><p><span data-ttu-id="91fa0-119">57500</span><span class="sxs-lookup"><span data-stu-id="91fa0-119">57500</span></span></p></td>
<td><p><span data-ttu-id="91fa0-120">8034</span><span class="sxs-lookup"><span data-stu-id="91fa0-120">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91fa0-121"><strong>Totals</strong></span><span class="sxs-lookup"><span data-stu-id="91fa0-121"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="91fa0-122">24730</span><span class="sxs-lookup"><span data-stu-id="91fa0-122">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="91fa0-123">오디오, 비디오 및 응용 프로그램 공유에 대한 포트 범위는 포트 40803에서 시작하여 총 24732개 포트를 포로합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-123">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="91fa0-124">원하는 경우 비즈니스용 Skype 서버 관리 셸 내에서 이와 유사한 명령을 실행하여 이러한 전체 포트 값을 사용하도록 특정 에지 서버를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-124">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Skype for Business Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="91fa0-125">또는 다음 명령을 사용하여 조직의 모든 에지 서버를 동시에 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-125">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="91fa0-126">다음 비즈니스용 Skype 서버 관리 셸 명령을 사용하여 에지 서버에 대한 현재 포트 설정을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-126">You can verify the current port settings for your Edge Servers by using this Skype for Business Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="91fa0-127">다시 말하면서 이러한 옵션을 제공하겠지만 포트 구성의 경우 그대로 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-127">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a><span data-ttu-id="91fa0-128">A/V 에지 서버에 대한 QoS 정책 구성</span><span class="sxs-lookup"><span data-stu-id="91fa0-128">Configure a QoS policy for your A/V Edge Servers</span></span>

<span data-ttu-id="91fa0-129">회의, 응용 프로그램 및 중재 서버용 QoS 정책을 만드는 것 외에도 A/V 에지 서버의 내부용으로 오디오 및 비디오 정책 역시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-129">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers.</span></span> <span data-ttu-id="91fa0-130">그러나 에지 서버에서 사용되는 정책은 회의, 응용 프로그램 및 중재 서버에서 사용되는 정책과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-130">However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="91fa0-131">회의, 응용 프로그램 및 중재 서버의 경우 원본 포트 범위를 지정했습니다. 에지 서버를 사용할 경우 대상 포트 범위를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-131">For the Conferencing, Application, and Mediation servers, you specified a source port range; with Edge servers, you need to specify a destination port range.</span></span> <span data-ttu-id="91fa0-132">따라서 회의, 응용 프로그램 및 중재 서버 QoS 정책을 에지 서버에 적용할 수 없습니다. 이러한 정책은 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-132">Because of this, you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work.</span></span> <span data-ttu-id="91fa0-133">대신 새 정책을 만들어 에지 서버에만 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-133">Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="91fa0-134">다음 절차에서는 에지 서버에서 서비스 품질을 관리하는 데 사용할 수 있는 Active Directory 그룹 정책 개체를 만드는 프로세스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-134">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers.</span></span> <span data-ttu-id="91fa0-135">물론 에지 서버가 Active Directory 계정을 포함하지 않는 독립 실행형 서버일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-135">Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts.</span></span> <span data-ttu-id="91fa0-136">이 경우에는 Active Directory 그룹 정책 대신 로컬 그룹 정책을 사용하면 되며, 두 경우의 차이점은 이러한 로컬 정책의 경우 로컬 그룹 정책 편집기를 사용하여 만들어야 하며 각 에지 서버에서 동일한 정책 집합을 개별적으로 만들어야 한다는 것뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-136">If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server.</span></span> <span data-ttu-id="91fa0-137">에지 서버에서 로컬 그룹 정책 편집기를 시작하고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-137">To start the Local Group Policy Editor on an Edge server, do the following:</span></span>

1.  <span data-ttu-id="91fa0-138">**시작** 을 클릭한 다음 **실행** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-138">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="91fa0-139">실행 **대화** 상자에서 **gpedit.msc를** 입력한 다음 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-139">In the **Run** dialog box, type **gpedit.msc**, and then press ENTER.</span></span>

<span data-ttu-id="91fa0-140">Active Directory 기반 정책을 만드는 경우에는 그룹 정책 관리가 설치된 컴퓨터에 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-140">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="91fa0-141">이 경우 그룹 정책 관리를 열고(시작, 관리 도구, 그룹 정책 관리를 클릭) 다음 단계를 완료합니다.  </span><span class="sxs-lookup"><span data-stu-id="91fa0-141">In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following steps:</span></span>

1.  <span data-ttu-id="91fa0-142">그룹 정책 관리에서 새 정책을 만들 컨테이너를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-142">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="91fa0-143">예를 들어 모든 비즈니스용 Skype 서버 컴퓨터가 비즈니스용 Skype 서버라는 OU에 있는 경우 비즈니스용 Skype 서버 OU에서 새 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-143">For example, if all your Skype for Business Server computers are located in an OU named Skype for Business Server, the new policy should be created in the Skype for Business Server OU.</span></span>

2.  <span data-ttu-id="91fa0-144">적절한 컨테이너를 마우스 오른쪽 단추로 클릭한 다음 이 도메인에서 GPO 만들기를 클릭하고 여기에 **연결합니다.**</span><span class="sxs-lookup"><span data-stu-id="91fa0-144">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="91fa0-145">새 **GPO** 대화 상자의 이름 상자에 새 그룹  정책 개체의 이름을 입력하고(예: 비즈니스용 **Skype 서버 오디오)** 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="91fa0-145">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Skype for Business Server Audio**), and then click **OK**.</span></span>

4.  <span data-ttu-id="91fa0-146">새로 만든 정책을 마우스 오른쪽 단추로 클릭한 다음 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="91fa0-146">Right-click the newly-created policy, and then click **Edit**.</span></span>

<span data-ttu-id="91fa0-147">여기서부터는 Active Directory 정책을 만들든 로컬 정책을 만들든 관계없이 프로세스가 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-147">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="91fa0-148">그룹 정책 관리 편집기 또는 로컬 그룹 정책 편집기에서 **컴퓨터 구성**, **정책**, **Windows 설정** 을 차례로 확장하고 **정책 기반 QoS** 를 마우스 오른쪽 단추로 클릭한 후에 **새 정책 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-148">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="91fa0-149">정책 기반 **QoS** 대화 상자의 열기 페이지에서 이름 상자에 새 정책의 이름(예: 비즈니스용 **Skype 서버 오디오)을** **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="91fa0-149">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Skype for Business Server Audio**) in the **Name** box.</span></span> <span data-ttu-id="91fa0-150">**DSCP 값 지정** 을 선택하고 값을 **46** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-150">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="91fa0-151">**아웃바운드 스로틀 속도 지정** 은 선택되지 않은 상태로 두고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-151">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="91fa0-152">다음 페이지에서 모든 응용  프로그램이 선택되어 있는지 확인한 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="91fa0-152">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="91fa0-153">이 설정은 특정 응용 프로그램이 만든 패킷만이 아니라 DSCP 표시가 46인 모든 패킷을 찾도록 네트워크에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-153">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="91fa0-154">세 번째 페이지에서 원본 **IP** 주소와 대상 **IP** 주소가 모두 선택되어 있는지 확인한 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="91fa0-154">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="91fa0-155">이러한 두 설정은 해당 패킷을 전송하는 컴퓨터(IP 주소) 및 패킷을 수신하는 컴퓨터(IP 주소)에 관계없이 패킷이 관리되도록 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-155">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="91fa0-156">4페이지에서는 **이 QoS 정책이 적용되는 프로토콜 선택** 드롭다운 목록에서 **TCP 및 UDP** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-156">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="91fa0-157">TCP(Transmission Control Protocol) 및 UDP(User Datagram Protocol)는 비즈니스용 Skype 서버 및 해당 클라이언트 응용 프로그램에서 가장 일반적으로 사용되는 두 가지 네트워킹 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-157">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

6.  <span data-ttu-id="91fa0-158">**대상 포트 번호 지정** 제목 아래에서 **이 대상 포트 또는 범위부터** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-158">Under the heading **Specify the destination port number**, select **From this destination port or range**.</span></span> <span data-ttu-id="91fa0-159">그 옆의 텍스트 상자에는 오디오 전송용으로 예약된 포트 범위를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-159">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="91fa0-160">예를 들어 오디오 트래픽에 대해 포트 49152 ~57500을 예약한 경우 다음 형식을 사용하여 포트 범위를 입력합니다. **49152:57500**.</span><span class="sxs-lookup"><span data-stu-id="91fa0-160">For example, if you reserved ports 49152 through ports 57500 for audio traffic, enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="91fa0-161">**마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-161">Click **Finish**.</span></span>

<span data-ttu-id="91fa0-162">오디오 트래픽에 대한 QoS 정책을 만든 후 비디오 트래픽에 대한 두 번째 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-162">After you have created the QoS policy for audio traffic, you should create a second policy for video traffic.</span></span> <span data-ttu-id="91fa0-163">비디오용 정책을 만들려면 오디오 정책을 만들 때 수행한 것과 기본적으로는 같은 절차를 따르되 다음 항목을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-163">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="91fa0-164">다른 고유한 정책 이름(예: 비즈니스용 **Skype 서버 비디오)을 사용하세요.**</span><span class="sxs-lookup"><span data-stu-id="91fa0-164">Use a different (and unique) policy name (for example, **Skype for Business Server Video**).</span></span>

  - <span data-ttu-id="91fa0-p113">DSCP 값을 46이 아닌 **34** 로 설정합니다. DSCP 값 34를 반드시 사용할 필요는 없습니다. 오디오에 사용한 것과는 다른 DSCP 값을 비디오에 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-p113">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="91fa0-168">비디오 트래픽에 대해 이전에 구성된 포트 범위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-168">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="91fa0-169">예를 들어 비디오용 포트 57501~65535를 예약한 경우 포트 범위를 **57501:65535로** 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-169">For example, if you have reserved ports 57501 through 65535 for video, set the port range to this: **57501:65535**.</span></span> <span data-ttu-id="91fa0-170">이 범위 역시 대상 포트 범위로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-170">Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="91fa0-171">응용 프로그램 공유 트래픽을 관리하기 위한 정책을 만드는 경우 세 번째 정책을 만들어 다음을 다음과 같이 대치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-171">If you decide to create a policy for managing application sharing traffic, you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="91fa0-172">다른 고유한 정책 이름(예: 비즈니스용 Skype 서버 응용 프로그램 **공유)을 사용하세요.**</span><span class="sxs-lookup"><span data-stu-id="91fa0-172">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="91fa0-p115">DSCP 값을 46이 아닌 **24** 로 설정합니다. DSCP 값 24를 반드시 사용할 필요는 없습니다. 오디오나 비디오에 사용한 것과는 다른 DSCP 값을 응용 프로그램 공유에 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-p115">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="91fa0-176">비디오 트래픽에 대해 이전에 구성된 포트 범위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-176">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="91fa0-177">예를 들어 응용 프로그램 공유를 위해 포트 40803~49151을 예약한 경우 포트 범위를 **40803:49151로** 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="91fa0-177">For example, if you have reserved ports 40803 through 49151 for application sharing, set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="91fa0-p117">새 정책은 에지 서버에서 그룹 정책을 새로 고쳐야 적용됩니다. 그룹 정책은 일정한 간격에 따라 자체적으로 새로 고쳐지기는 하지만, 그룹 정책을 새로 고쳐야 하는 각 컴퓨터에서 다음 명령을 실행하면 그룹 정책을 강제로 즉시 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-p117">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="91fa0-180">이 명령은 비즈니스용 Skype 서버 내에서 또는 관리자 자격 증명으로 실행되는 모든 명령 창에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-180">This command can be run from within the Skype for Business Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="91fa0-181">관리자 자격 증명을 사용한 명령 창을 실행하려면 **시작** 을 클릭하고 **명령 프롬프트** 를 마우스 오른쪽 단추로 클릭한 후 **관리자 권한으로 실행** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-181">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="91fa0-182">에지 서버를 실행한 후에도 에지 서버를 다시 Gpudate.exe.</span><span class="sxs-lookup"><span data-stu-id="91fa0-182">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="91fa0-183">네트워크 패킷이 적절한 DSCP 값으로 표시되도록 하려면 다음 절차를 완료하여 각 컴퓨터에서 새 레지스트리 항목도 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-183">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="91fa0-184">**시작** 을 클릭한 다음 **실행** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-184">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="91fa0-185">실행 **대화** 상자에서 **regedit를** 입력한 다음 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-185">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="91fa0-186">레지스트리 편집기에서 **HKEY \_ LOCAL \_ MACHINE,** **SYSTEM,** **CurrentControlSet,** 서비스를 확장한 다음 **Tcpip을 확장합니다.** </span><span class="sxs-lookup"><span data-stu-id="91fa0-186">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="91fa0-187">**Tcpip** 를 마우스 오른쪽 단추로 클릭하고 **새로 만들기** 를 가리킨 다음 **키** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-187">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="91fa0-188">새 레지스트리 키를 만든 후 **QoS를** 입력한 다음 Enter 키를 눌러 키 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-188">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="91fa0-189">**QoS** 를 마우스 오른쪽 단추로 클릭하고 **새로 만들기** 를 가리킨 다음 **문자열 값** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-189">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="91fa0-190">새 레지스트리 값을 만든 후 **NLA를** 사용하지 말고 Enter를 눌러 값 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-190">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="91fa0-191">**NLA 사용 안 함** 을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="91fa0-191">Double-click **Do no use NLA**.</span></span> <span data-ttu-id="91fa0-192">문자열 **편집** 대화 상자에서 값 데이터  **상자에 1을** 입력한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="91fa0-192">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="91fa0-193">레지스트리 편집기를 닫고 컴퓨터를 다시 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="91fa0-193">Close the Registry Editor and reboot your computer.</span></span>
