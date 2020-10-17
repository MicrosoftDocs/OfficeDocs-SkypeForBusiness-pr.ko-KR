---
title: 'Lync Server 2013: Lync VDI 플러그 인 문제 해결'
description: 'Lync Server 2013: Lync VDI 플러그 인 문제 해결'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting the Lync VDI plug-in
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204713(v=OCS.15)
ms:contentKeyID: 48183525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cd2c0e3c8a47225f00ce280706dea2287e4dc8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548944"
---
# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="3b4d0-103">Lync Server 2013에서 Lync VDI 플러그 인 문제 해결</span><span class="sxs-lookup"><span data-stu-id="3b4d0-103">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b4d0-104">_**마지막으로 수정 된 항목:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="3b4d0-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a><span data-ttu-id="3b4d0-105">씬 클라이언트에 Lync VDI 플러그 인을 설치할 때 발생 하는 문제 해결</span><span class="sxs-lookup"><span data-stu-id="3b4d0-105">Troubleshooting Issues with Installing the Lync VDI Plug-in on a Thin Client</span></span>

<span data-ttu-id="3b4d0-106">씬 클라이언트에서 VDI 플러그 인을 설치할 때 문제가 발생하면 다음 사항을 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="3b4d0-106">If there are issues with installing the VDI plug-in on a thin client, check the following:</span></span>

  - <span data-ttu-id="3b4d0-107">TEMP 및 TMP 시스템 변수에 지정한 폴더에 충분한 공간이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3b4d0-107">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>

  - <span data-ttu-id="3b4d0-p101">쓰기 금지가 해제되어 있는지 확인합니다. 관련 지침은 장치 제조업체 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3b4d0-p101">Ensure that write-protect is turned off. Refer to your device manufacturer’s documentation for instructions.</span></span>

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="3b4d0-110">페어링 관련 문제 해결</span><span class="sxs-lookup"><span data-stu-id="3b4d0-110">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="3b4d0-111">VDI 플러그 인 페어링이 실패하면 오른쪽 아래의 페어링 아이콘이 다음과 같이 빨간색 "X"로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b4d0-111">When VDI plug-in pairing fails, the pairing icon in the lower right displays as a red “X” as shown:</span></span>

<span data-ttu-id="3b4d0-112">![성공적인 페어링을 보여 주는 Lync VDI 아이콘](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "성공적인 페어링을 보여 주는 Lync VDI 아이콘")</span><span class="sxs-lookup"><span data-stu-id="3b4d0-112">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>

<span data-ttu-id="3b4d0-113">실패의 가능한 원인 및 취할 수 있는 해결 조치는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3b4d0-113">The following are possible reasons for failures and the corrective actions you can take.</span></span>

  - <span data-ttu-id="3b4d0-114">**사용자가 로그인 중에 잘못된 자격 증명을 입력함**</span><span class="sxs-lookup"><span data-stu-id="3b4d0-114">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="3b4d0-115">사용자가 Lync에서 로그 아웃 하 고 올바른 자격 증명으로 다시 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b4d0-115">The user should sign out of Lync and sign in again with the correct credentials.</span></span> <span data-ttu-id="3b4d0-116">그러면 페어링 대화 상자가 다시 나타나고 페어링 성공 여부가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b4d0-116">The pairing dialog box will reappear and show whether pairing is successful.</span></span>

  - <span data-ttu-id="3b4d0-117">**다른 원격 데스크톱 클라이언트 인스턴스가 실행되고 있음**</span><span class="sxs-lookup"><span data-stu-id="3b4d0-117">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="3b4d0-118">Windows에서 원격 데스크톱 연결을 사용 하는 경우 사용자는 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b4d0-118">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
    1.  <span data-ttu-id="3b4d0-119">**Alt+Ctrl+Delete**를 누르고 **작업 관리자 시작**을 클릭하여 작업 관리자를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3b4d0-119">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
    2.  <span data-ttu-id="3b4d0-120">**프로세스** 탭을 클릭하고 목록에서 이름이 **mstsc.exe**인 모든 프로세스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3b4d0-120">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
    3.  <span data-ttu-id="3b4d0-121">각 **mstsc.exe** 프로세스를 강조 표시하고 **프로세스 끝내기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3b4d0-121">Highlight each **mstsc.exe** process and then click **End Process**.</span></span>
    
    4.  <span data-ttu-id="3b4d0-122">새 원격 데스크톱 세션을 시작하고 다시 연결해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="3b4d0-122">Start a new remote desktop session and try connecting again.</span></span>

  - <span data-ttu-id="3b4d0-123">**필요한 파일이 올바르게 설치되지 않음**</span><span class="sxs-lookup"><span data-stu-id="3b4d0-123">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="3b4d0-124">로컬 컴퓨터에 플러그 인을 설치한 후에는 다음 파일이 C: \\ Program files \\ Microsoft Office \\ office15.adml (또는 적절 한 드라이브 문자) 아래에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b4d0-124">After the plug-in is installed on the local computer, the following files should be present under C:\\Program Files\\Microsoft Office\\Office15 (or the appropriate drive letter):</span></span>
    
      - <span data-ttu-id="3b4d0-125">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="3b4d0-125">LyncVdiPlugin.dll</span></span>
    
      - <span data-ttu-id="3b4d0-126">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="3b4d0-126">UcVdi.dll</span></span>
    
    <span data-ttu-id="3b4d0-127">VDI 페어링에 문제가 있는 경우 로컬 컴퓨터에 이러한 파일이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3b4d0-127">If there are any issues with VDI pairing, check to make sure that these files are present on the local computer.</span></span>

  - <span data-ttu-id="3b4d0-128">**Lync 클라이언트가 로컬 컴퓨터에서 실행 되 고 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="3b4d0-128">**The Lync client is running on the local computer.**</span></span>
    
    <span data-ttu-id="3b4d0-129">Lync VDI 플러그 인을 사용 하려면 Lync 클라이언트가 로컬 컴퓨터에서 실행 되 고 있지 않으면 연결이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b4d0-129">To use the Lync VDI plugin, a Lync client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="3b4d0-130">가장 좋은 방법은 사용자가 로컬 컴퓨터에 Lync 클라이언트를 설치 하지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3b4d0-130">As a best practice, the user should not install a Lync client on the local computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

