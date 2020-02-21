---
title: 'Lync Server 2013: 사용자 지정 현재 상태 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring custom presence states
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398997(v=OCS.15)
ms:contentKeyID: 48185534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f93229ee06a3d45db2478003a18ac22a2e7cf59
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-custom-presence-states-in-lync-server-2013"></a><span data-ttu-id="8c702-102">Lync Server 2013에서 사용자 지정 현재 상태 구성</span><span class="sxs-lookup"><span data-stu-id="8c702-102">Configuring custom presence states in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c702-103">_**마지막으로 수정 된 항목:** 2013-01-10_</span><span class="sxs-lookup"><span data-stu-id="8c702-103">_**Topic Last Modified:** 2013-01-10_</span></span>

<span data-ttu-id="8c702-104">Lync 2013에서 사용자 지정 현재 상태를 정의 하려면 XML 사용자 지정 현재 상태 구성 파일을 만든 다음 Lync Server 관리 셸 cmdlet **New-csclientpolicy** 또는 Parameter CustomStateURL과 함께 **csclientpolicy** 를 사용 하 여 해당 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c702-104">To define custom presence states in Lync 2013, create an XML custom presence configuration file, and then specify its location by using the Lync Server Management Shell cmdlets **New-CSClientPolicy** or **Set-CSClientPolicy** with the parameter CustomStateURL.</span></span>

<span data-ttu-id="8c702-105">구성 파일에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c702-105">Configuration files have the following properties:</span></span>

  - <span data-ttu-id="8c702-106">사용자 지정 현재 상태는 사용 가능, 사용 중, 방해 금지 상태 표시기로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c702-106">Custom presence states can be configured with the Available, Busy, and Do Not Disturb presence indicators.</span></span>

  - <span data-ttu-id="8c702-107">Availability 특성은 사용자 지정 상태의 상태 텍스트와 연결 된 현재 상태 표시기를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c702-107">The availability attribute determines which presence indicator is associated with the status text of the custom state.</span></span> <span data-ttu-id="8c702-108">이 항목 뒷부분의 예제에서는 집에서 작업 상태 텍스트가 녹색 (사용 가능) 현재 표시기 오른쪽에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c702-108">In the example later in this topic, the status text Working from Home is displayed to the right of the green (Available) presence indicator.</span></span>

  - <span data-ttu-id="8c702-109">상태 텍스트의 최대 길이는 64 자입니다.</span><span class="sxs-lookup"><span data-stu-id="8c702-109">The maximum length of the status text is 64 characters.</span></span>

  - <span data-ttu-id="8c702-110">사용자 지정 현재 상태를 최대 4 개까지 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c702-110">A maximum of four custom presence states can be added.</span></span>

  - <span data-ttu-id="8c702-111">CustomStateURL 매개 변수는 구성 파일의 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c702-111">The CustomStateURL parameter specifies the location of the configuration file.</span></span> <span data-ttu-id="8c702-112">Lync 2013에서 SIP 고급 보안 모드는 기본적으로 사용 하도록 설정 되어 있으므로 HTTPS를 사용 하도록 설정 된 웹 서버에 사용자 지정 현재 상태 구성 파일을 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c702-112">In Lync 2013, SIP high security mode is enabled by default, so you will need to store the custom presence configuration file on a web server that has HTTPS enabled.</span></span> <span data-ttu-id="8c702-113">그렇지 않으면 Lync 2013 클라이언트가 해당 클라이언트에 연결할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c702-113">Otherwise, Lync 2013 clients will be unable to connect to it.</span></span> <span data-ttu-id="8c702-114">예를 들어 유효한 주소는 `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`입니다.</span><span class="sxs-lookup"><span data-stu-id="8c702-114">For example, a valid address would be `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8c702-115">프로덕션 환경에서는 권장 되지 않지만 EnableSIPHighSecurityMode 레지스트리 설정을 사용 하 여 클라이언트에서 SIP 고급 보안 모드를 사용 하지 않도록 설정 하 여 HTTPS가 아닌 파일 공유에 있는 구성 파일을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c702-115">Although it is not recommended in a production environment, you can test a configuration file that is located on a non-HTTPS file share by using the EnableSIPHighSecurityMode registry setting to disable SIP high security mode on the client.</span></span> <span data-ttu-id="8c702-116">그런 다음 CustomStateURL 레지스트리 설정을 사용 하 여 구성 파일에 대해 HTTPS가 아닌 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c702-116">Then you can use the CustomStateURL registry setting to specify a non-HTTPS location for the configuration file.</span></span> <span data-ttu-id="8c702-117">Lync 2013는 Lync 2010 레지스트리 설정을 준수 하지만 레지스트리 하이브가 업데이트 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8c702-117">Note that Lync 2013 honors Lync 2010 registry settings, but the registry hive has been updated.</span></span> <span data-ttu-id="8c702-118">레지스트리 설정은 다음과 같이 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c702-118">You would create the registry settings as follows:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="8c702-119">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span><span class="sxs-lookup"><span data-stu-id="8c702-119">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span></span></P>
> <P><span data-ttu-id="8c702-120">형식: DWORD</span><span class="sxs-lookup"><span data-stu-id="8c702-120">Type: DWORD</span></span></P>
> <P><span data-ttu-id="8c702-121">값 데이터: 0</span><span class="sxs-lookup"><span data-stu-id="8c702-121">Value data: 0</span></span></P>
> <LI>
> <P><span data-ttu-id="8c702-122">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span><span class="sxs-lookup"><span data-stu-id="8c702-122">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span></span></P>
> <P><span data-ttu-id="8c702-123">Type: String (REG_SZ)</span><span class="sxs-lookup"><span data-stu-id="8c702-123">Type: String (REG_SZ)</span></span></P>
> <P><span data-ttu-id="8c702-124">값 데이터 (예): file://\\lspool com\LSFileShare\ClientConfigFolder\Presence.xml 또는 file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span><span class="sxs-lookup"><span data-stu-id="8c702-124">Value data (examples): file://\\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml or file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span></span></P></LI></UL>



</div>

<span data-ttu-id="8c702-125">XML 구성 파일에 하나 이상의 LCID (로캘 ID) 스키마를 지정 하 여 사용자 지정 현재 상태를 지역화 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c702-125">Localize your custom presence state by specifying one or more locale ID (LCID) schema in the XML configuration file.</span></span> <span data-ttu-id="8c702-126">이 항목의 뒷부분에 나오는 예제에서는 영어-미국 (1033), 노르웨이어-복말 (1044), 프랑스어-프랑스 (1036) 및 터키어 (1055)로 지역화 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8c702-126">The example later in this topic shows localization into English - United States (1033), Norwegian - Bokmål (1044), French - France (1036), and Turkish (1055).</span></span> <span data-ttu-id="8c702-127">Lcid 목록은 Microsoft에서 할당 한 로캘 Id를 참조 하십시오 <https://go.microsoft.com/fwlink/p/?linkid=157331>.</span><span class="sxs-lookup"><span data-stu-id="8c702-127">For a list of LCIDs, see Locale IDs Assigned by Microsoft at <https://go.microsoft.com/fwlink/p/?linkid=157331>.</span></span>

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a><span data-ttu-id="8c702-128">Lync 2013에 사용자 지정 현재 상태를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="8c702-128">To add custom presence states to Lync 2013</span></span>

1.  <span data-ttu-id="8c702-129">다음 예제의 형식을 사용 하는 XML 구성 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8c702-129">Create an XML configuration file that uses the format of the following example:</span></span>
    
        <?xml version="1.0"?>
        <customStates xmlns="http://schemas.microsoft.com/09/2009/communicator/customStates">
          <customState ID="1" availability="online">
            <activity LCID="1033">Working from Home</activity>
            <activity LCID="1044">activity 2 for 1044</activity>
            <activity LCID="1055">activity 3 for 1055</activity>
          </customState>
          <customState ID="2" availability="busy">
            <activity LCID="1033">In a Live Meeting</activity>
            <activity LCID="1036">Equivalent French String for - In a Live Meeting </activity>
          </customState>
          <customState ID="3" availability="busy">
            <activity LCID="1033">Meeting with Customer</activity>
            <activity LCID="1055">meeting with client</activity>
            <activity LCID="1036">Equivalent French String for - Meeting with Customer</activity>
          </customState>
          <customState ID="4" availability="do-not-disturb">
            <activity LCID="1033">Interviewing</activity>
          </customState>
        </customStates>

2.  <span data-ttu-id="8c702-130">HTTPS를 사용 하도록 설정 된 웹 서버에 XML 구성 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c702-130">Save the XML configuration file to a web server with HTTPS enabled.</span></span> <span data-ttu-id="8c702-131">이 예제에서는 파일 이름이 system.xml이 고 위치 https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml에 저장 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c702-131">In this example, the file is named Presence.xml and saved to the location https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.</span></span>

3.  <span data-ttu-id="8c702-132">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8c702-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="8c702-133">Lync Server 관리 셸에서 다음과 같은 명령을 사용 하 여 XML 구성 파일의 위치를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c702-133">In the Lync Server Management Shell, define the location of your XML configuration file by using a command similar to the following:</span></span>
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  <span data-ttu-id="8c702-134">**부여-CSClientPolicy** cmdlet을 사용 하 여 사용자에 게이 새 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c702-134">Use the **Grant-CSClientPolicy** cmdlet to assign this new policy to users.</span></span>

<span data-ttu-id="8c702-135">자세한 내용은 Lync Server 관리 셸 설명서에서 [New-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) 및 [Grant-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8c702-135">For details, see [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) and [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="8c702-136">기본적으로 Lync Server 2013&nbsp;는 3 시간 마다 클라이언트 정책과 설정을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c702-136">By default, Lync Server 2013&nbsp;updates client policies and settings every three hours.</span></span></P>
> <LI>
> <P><span data-ttu-id="8c702-137">CustomStateURL과 같은 이전 릴리스의 그룹 정책 설정을 계속 사용 하려면 Lync 2013이 새 정책 레지스트리 하이브에 있는 경우 (HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync) 설정을 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c702-137">If you want to continue using Group Policy settings from previous releases, such as CustomStateURL, Lync 2013 will recognize the settings if they are located in the new policy registry hive (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync).</span></span> <span data-ttu-id="8c702-138">그러나 서버 기반 클라이언트 정책이 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c702-138">However, server-based client policies take precedence.</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

