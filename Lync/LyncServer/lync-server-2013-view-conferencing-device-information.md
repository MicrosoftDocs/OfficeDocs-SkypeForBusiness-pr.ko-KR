---
title: 'Lync Server 2013: 회의 장치 정보 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View conferencing device information
ms:assetid: 838bdbf8-8b68-4eb6-8fa3-45bfd5b0b1cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994043(v=OCS.15)
ms:contentKeyID: 51803954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5355ae418e53c44cc61340b57910993ac2afea2c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-conferencing-device-information-in-lync-server-2013"></a><span data-ttu-id="1b09f-102">Lync Server 2013에서 회의 장치 정보 보기</span><span class="sxs-lookup"><span data-stu-id="1b09f-102">View conferencing device information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b09f-103">_**마지막으로 수정한 주제:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="1b09f-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="1b09f-104">Windows PowerShell 및 **CsMeetingRoom** cmdlet을 사용 하 여 조직에서 사용 하도록 구성 된 회의 장치에 대 한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b09f-104">You can view information about the conferencing devices configured for use in your organization by using Windows PowerShell and the **Get-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="1b09f-105">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 **CsMeetingRoom** cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b09f-105">Run the **Get-CsMeetingRoom** cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1b09f-106">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1b09f-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="1b09f-107">매개 변수 없이 **Get-CsMeetingRoom** cmdlet을 사용 하는 경우 모든 회의 장치에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b09f-107">If you use the **Get-CsMeetingRoom** cmdlet without any parameters, it returns information about all your conferencing devices.</span></span> <span data-ttu-id="1b09f-108">선택적 매개 변수는 다양 한 방법으로 정보를 필터링 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b09f-108">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="1b09f-109">자세한 내용은 Get-help의 Parameters 섹션 [CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1b09f-109">For details, see the Parameters section of [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom).</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-conferencing-devices"></a><span data-ttu-id="1b09f-110">모든 회의 장치에 대 한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="1b09f-110">Viewing Information about All Your Conferencing Devices</span></span>

  - <span data-ttu-id="1b09f-111">모든 회의 장치에 대 한 세부 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1b09f-111">To view details about all your conferencing devices, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsMeetingRoom
    
    <span data-ttu-id="1b09f-112">이 cmdlet은 각 회의 장치에 대해 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b09f-112">This cmdlet returns information similar to the following for each conferencing device.</span></span> <span data-ttu-id="1b09f-113">이 예제에서는이 cmdlet을 실행할 때 표시 되는 정보만 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1b09f-113">Note that this example shows only some of the information that you’ll see when you run this cmdlet:</span></span>
    
        ContactOptionFlags                : 64
        OwnerUrn                          : urn:device:roomsystem
        OriginatorSid                     :
        SamAccountName                    : room12129
        UserPrincipalName                 : room1219@litwareinc.com
        FirstName                         : 
        LastName                          :
        WindowsEmailAddress               :
        Sid                               : S-1-5-21-2831376166-2963252556-2165051629-1257
        LineServerURI                     :
        AudioVideoDisabled                : False
        IPPBXSoftPhoneRoutingEnabled      : False
        RemoteCallControlTelephonyEnabled : False
        PrivateLine                       :
        AcpInfo                           : {}
        HostedVoiceMail                   :
        DisplayName                       : Room 1219

</div>

<div>

## <a name="viewing-information-about-a-specific-conferencing-device"></a><span data-ttu-id="1b09f-114">특정 회의 장치에 대 한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="1b09f-114">Viewing Information about a Specific Conferencing Device</span></span>

  - <span data-ttu-id="1b09f-115">특정 회의 장치에 대 한 정보를 보려면 Id 매개 변수 뒤에 회의 장치 id (일반적으로 Active Directory 표시 이름)를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b09f-115">To view information for a specific conferencing device, include the Identity parameter followed by the conferencing device identity (typically, the Active Directory display name).</span></span> <span data-ttu-id="1b09f-116">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1b09f-116">For example:</span></span>
    
        Get-CsMeetingRoom -Identity "Room 1219"

</div>

<span data-ttu-id="1b09f-117">자세한 내용은 Get-help cmdlet에 대 한 도움말 항목을 [CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="1b09f-117">For details, see the Help topic for the [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

