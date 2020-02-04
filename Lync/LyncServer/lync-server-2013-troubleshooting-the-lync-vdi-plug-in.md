---
title: 'Lync Server 2013: Lync VDI 플러그 인 문제 해결'
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
ms.openlocfilehash: f1dfd8082ef0f0cdfc2a7931a675398507daaa51
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="3fbdb-102">Lync Server 2013에서 Lync VDI 플러그 인 문제 해결</span><span class="sxs-lookup"><span data-stu-id="3fbdb-102">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3fbdb-103">_**마지막으로 수정한 주제:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="3fbdb-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a><span data-ttu-id="3fbdb-104">씬 클라이언트에 Lync VDI 플러그 인 설치 문제 해결</span><span class="sxs-lookup"><span data-stu-id="3fbdb-104">Troubleshooting Issues with Installing the Lync VDI Plug-in on a Thin Client</span></span>

<span data-ttu-id="3fbdb-105">씬 클라이언트에 VDI 플러그 인을 설치 하는 데 문제가 있는 경우 다음을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="3fbdb-105">If there are issues with installing the VDI plug-in on a thin client, check the following:</span></span>

  - <span data-ttu-id="3fbdb-106">TEMP 및 TMP 시스템 변수에 지정한 폴더에 충분 한 공간이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbdb-106">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>

  - <span data-ttu-id="3fbdb-107">쓰기 방지가 꺼져 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbdb-107">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="3fbdb-108">자세한 내용은 장치 제조업체의 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3fbdb-108">Refer to your device manufacturer’s documentation for instructions.</span></span>

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="3fbdb-109">페어링 문제 해결</span><span class="sxs-lookup"><span data-stu-id="3fbdb-109">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="3fbdb-110">VDI 플러그 인 페어링에 실패 하는 경우 오른쪽 아래에 있는 페어링 아이콘은 표시 된 대로 빨간색 "X"로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fbdb-110">When VDI plug-in pairing fails, the pairing icon in the lower right displays as a red “X” as shown:</span></span>

<span data-ttu-id="3fbdb-111">![성공적인 연결을 보여 주는 Lync VDI 아이콘](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "성공적인 연결을 보여 주는 Lync VDI 아이콘")</span><span class="sxs-lookup"><span data-stu-id="3fbdb-111">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>

<span data-ttu-id="3fbdb-112">다음은 실패 및 정정 작업에 발생할 수 있는 원인입니다.</span><span class="sxs-lookup"><span data-stu-id="3fbdb-112">The following are possible reasons for failures and the corrective actions you can take.</span></span>

  - <span data-ttu-id="3fbdb-113">**로그인 하는 동안 사용자가 잘못 된 자격 증명을 입력 했습니다.**</span><span class="sxs-lookup"><span data-stu-id="3fbdb-113">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="3fbdb-114">사용자는 Lync에서 로그 아웃 하 고 올바른 자격 증명으로 다시 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbdb-114">The user should sign out of Lync and sign in again with the correct credentials.</span></span> <span data-ttu-id="3fbdb-115">페어링 대화 상자가 다시 표시 되 고 페어링이 성공할 수 있는지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3fbdb-115">The pairing dialog box will reappear and show whether pairing is successful.</span></span>

  - <span data-ttu-id="3fbdb-116">**원격 데스크톱 클라이언트의 다른 인스턴스가 실행 중입니다.**</span><span class="sxs-lookup"><span data-stu-id="3fbdb-116">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="3fbdb-117">Windows에서 원격 데스크톱 연결을 사용 하는 경우 사용자는 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbdb-117">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
    1.  <span data-ttu-id="3fbdb-118">작업 관리자 시작: **Alt + Ctrl + Delete**를 누른 다음 **작업 관리자 시작**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbdb-118">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
    2.  <span data-ttu-id="3fbdb-119">**프로세스** 탭을 클릭 하 고 목록에서 **mstsc** 라는 모든 프로세스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3fbdb-119">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
    3.  <span data-ttu-id="3fbdb-120">각 **mstsc** 프로세스를 강조 표시 한 다음 **프로세스 끝내기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbdb-120">Highlight each **mstsc.exe** process and then click **End Process**.</span></span>
    
    4.  <span data-ttu-id="3fbdb-121">새 원격 데스크톱 세션을 시작 하 고 다시 연결 해 보세요.</span><span class="sxs-lookup"><span data-stu-id="3fbdb-121">Start a new remote desktop session and try connecting again.</span></span>

  - <span data-ttu-id="3fbdb-122">**필요한 파일이 올바르게 설치 되지 않았습니다.**</span><span class="sxs-lookup"><span data-stu-id="3fbdb-122">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="3fbdb-123">로컬 컴퓨터에 플러그 인을 설치한 후에는 C:\\Program Files\\Microsoft Office\\Office15 (또는 적절 한 드라이브 문자) 아래에 다음 파일이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fbdb-123">After the plug-in is installed on the local computer, the following files should be present under C:\\Program Files\\Microsoft Office\\Office15 (or the appropriate drive letter):</span></span>
    
      - <span data-ttu-id="3fbdb-124">LyncVdiPlugin</span><span class="sxs-lookup"><span data-stu-id="3fbdb-124">LyncVdiPlugin.dll</span></span>
    
      - <span data-ttu-id="3fbdb-125">(Vdi) dll</span><span class="sxs-lookup"><span data-stu-id="3fbdb-125">UcVdi.dll</span></span>
    
    <span data-ttu-id="3fbdb-126">VDI 페어링에 문제가 있는 경우 이러한 파일이 로컬 컴퓨터에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbdb-126">If there are any issues with VDI pairing, check to make sure that these files are present on the local computer.</span></span>

  - <span data-ttu-id="3fbdb-127">**Lync 클라이언트가 로컬 컴퓨터에서 실행 되 고 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="3fbdb-127">**The Lync client is running on the local computer.**</span></span>
    
    <span data-ttu-id="3fbdb-128">Lync VDI 플러그 인을 사용 하려면 Lync 클라이언트가 로컬 컴퓨터에서 실행 되 고 있지 않아야 하 고, 그렇지 않으면 연결에 실패 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fbdb-128">To use the Lync VDI plugin, a Lync client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="3fbdb-129">가장 좋은 방법은 사용자가 로컬 컴퓨터에 Lync 클라이언트를 설치 하지 않아야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3fbdb-129">As a best practice, the user should not install a Lync client on the local computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

