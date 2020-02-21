---
title: 'Lync Server 2013: Operation Manager 에이전트 파일 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Operation Manager agent files
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48185692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e685abf7916c446bf9acf73e50f5633271b2942
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a><span data-ttu-id="11e22-102">Lync Server 2013에서 Operation Manager 에이전트 파일 설치</span><span class="sxs-lookup"><span data-stu-id="11e22-102">Installing the Operation Manager agent files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11e22-103">_**마지막으로 수정 된 항목:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="11e22-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="11e22-104">컴퓨터에 Operations Manager 에이전트 파일을 설치하려면 다음 단계를 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="11e22-104">To install the Operations Manager agent files on the computer, complete the following steps.</span></span>

1.  <span data-ttu-id="11e22-105">System Center 설치 미디어에서 **SetupOM.exe**를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="11e22-105">On your System Center setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="11e22-106">System Center Operation Manager 설치 프로그램에서 **Operations Manager 에이전트 설치(Install Operations Manager Agent)** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="11e22-106">In System Center Operation Manager setup, click **Install Operations Manager Agent**.</span></span>

3.  <span data-ttu-id="11e22-107">System Center 설치 마법사의 **System Center Operations Manager 설치 시작(Welcome to the System Center Operations Manager Setup)** 마법사 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="11e22-107">In System Center Setup wizard, on the **Welcome to the System Center Operations Manager Setup** wizard page, click **Next**.</span></span>

4.  <span data-ttu-id="11e22-108">**대상 폴더** 페이지에서 Operations Manager 에이전트 파일이 설치될 폴더를 선택하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="11e22-108">On the **Destination Folder** page, select the folder where the Operations Manager Agent files will be installed, and then click **Next**.</span></span>

5.  <span data-ttu-id="11e22-109">**관리 그룹 구성** 페이지에서 **관리 그룹 정보 지정**을 선택하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="11e22-109">On the **Management Group Configuration** page, select **Specify Management Group information**, and then click **Next**.</span></span>

6.  <span data-ttu-id="11e22-p101">**관리 그룹 구성** 페이지의 **관리 그룹 이름** 상자에 Operations Manager 관리 그룹의 이름을 입력하고 **관리 서버** 상자에 Operations Manager 서버의 이름(예: atl-scom-001)을 입력합니다. Operations Manager에 사용되는 포트 번호를 변경한 경우 관리 서버 포트 상자에 새 포트 번호를 입력합니다. 그렇지 않으면 기본값인 5723을 포트로 그대로 사용하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="11e22-p101">On the **Management Group Configuration** page, type the name of your Operations Manager Management Group in the **Management Group Name** box, and then type the host name of your Operations Manager server (for example, atl-scom-001) in the **Management Server** box. If you have changed the port number used by Operations Manager, then type the new port number in the Management Server Port box. Otherwise, leave the port at the default value of 5723 and click **Next**.</span></span>

7.  <span data-ttu-id="11e22-113">**에이전트 작업 계정** 페이지에서 **로컬 시스템**을 선택하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="11e22-113">On the **Agent Action Account** page, select **Local System**, and then click **Next**.</span></span>

8.  <span data-ttu-id="11e22-114">**Microsoft Update** 페이지에서 **Microsoft Update 사용 안 함(I don't want to use Microsoft Update)** 을 선택하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="11e22-114">On the **Microsoft Update** page, select **I don't want to use Microsoft Update**, and then click **Next**.</span></span>

9.  <span data-ttu-id="11e22-115">**설치 준비 완료** 페이지에서 **설치**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="11e22-115">On the **Ready to Install** page, click **Install**.</span></span>

10. <span data-ttu-id="11e22-116">**System Center Operations Manager 설치 마법사 완료 중(Completing the System Center Operations Manager Setup wizard)** 페이지에서 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="11e22-116">On the **Completing the System Center Operations Manager Setup wizard** page, click **Finish**.</span></span>

11. <span data-ttu-id="11e22-117">**끝내기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="11e22-117">Click **Exit**.</span></span>

<span data-ttu-id="11e22-118">System Center 2007 R2를 사용하는 경우 **시작**, **모든 프로그램**, **System Center Operations Manager 2007 R2** 및 **Operations Manager Shell**을 차례대로 클릭하여 에이전트가 만들어졌는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11e22-118">If you are using System Center 2007 R2, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking **System Center Operations Manager 2007 R2**, and then clicking **Operations Manager Shell**.</span></span> <span data-ttu-id="11e22-119">Operations Manager 셸에서 다음 Windows PowerShell 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="11e22-119">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-Agent 

<span data-ttu-id="11e22-120">모든 Operations Manager 에이전트 목록이 화면에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="11e22-120">A list of all your Operations Manager agents will appear onscreen.</span></span>

<span data-ttu-id="11e22-121">System Center 2012를 사용하는 경우 Operations 2012 Manager Shell에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="11e22-121">If you are using System Center 2012, run this command from the Operations 2012 Manager Shell:</span></span>

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

