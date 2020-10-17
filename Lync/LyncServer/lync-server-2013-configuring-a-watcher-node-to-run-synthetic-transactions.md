---
title: 'Lync Server 2013: 가상 트랜잭션을 실행 하도록 감시자 노드 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to run synthetic transactions
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205314(v=OCS.15)
ms:contentKeyID: 48185578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9514099b3981dafdbb34911d0cedd249221c5621
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499105"
---
# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="8e908-102">Lync Server 2013에서 가상 트랜잭션을 실행 하도록 감시자 노드 구성</span><span class="sxs-lookup"><span data-stu-id="8e908-102">Configuring a watcher node to run synthetic transactions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e908-103">_**마지막으로 수정 된 항목:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="8e908-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="8e908-104">System Center 에이전트 파일을 설치한 후에는 다음에 감시자 노드 자체를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e908-104">After the System Center agent files have been installed, you must next configure the watcher node itself.</span></span> <span data-ttu-id="8e908-105">감시자 노드를 구성 하기 위해 수행 하는 단계는 감시자 노드 컴퓨터가 경계 네트워크 내에 있는지 아니면 경계 네트워크 외부에 있는 지에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="8e908-105">The steps you take to configure a watcher node will vary depending on whether your watcher node computer lies inside your perimeter network or outside your perimeter network.</span></span>

<span data-ttu-id="8e908-106">감시자 노드를 구성할 때는 해당 노드에서 사용할 인증 방법의 유형도 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e908-106">When you configure a watcher node, you must also choose the type of authentication method to be employed by that node.</span></span> <span data-ttu-id="8e908-107">Lync Server 2013에서는 신뢰할 수 있는 서버 또는 자격 증명 인증 이라는 두 가지 인증 방법 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e908-107">Lync Server 2013 enables you to choose one of two authentication methods: Trusted Server or Credential Authentication.</span></span> <span data-ttu-id="8e908-108">다음 표에서는 이러한 두 방법의 차이점에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e908-108">The differences between these two methods are outlined in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e908-109">구성</span><span class="sxs-lookup"><span data-stu-id="8e908-109">Configuration</span></span></th>
<th><span data-ttu-id="8e908-110">설명</span><span class="sxs-lookup"><span data-stu-id="8e908-110">Description</span></span></th>
<th><span data-ttu-id="8e908-111">지원 되는 위치</span><span class="sxs-lookup"><span data-stu-id="8e908-111">Locations Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e908-112">신뢰할 수 있는 서버</span><span class="sxs-lookup"><span data-stu-id="8e908-112">Trusted Server</span></span></p></td>
<td><p><span data-ttu-id="8e908-113">인증서를 사용 하 여 내부 서버를 가장 하 고 인증 문제를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e908-113">Uses a certificate to impersonate an internal server and bypass authentication challenges.</span></span></p>
<p><span data-ttu-id="8e908-114">이 기능은 각 감시자 노드에서 많은 사용자 암호를 사용 하지 않고 단일 인증서를 관리 하려는 관리자에 게 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e908-114">This is useful for administrators who would prefer to manage a single certificate instead of many user passwords on each watcher node.</span></span></p></td>
<td><p><span data-ttu-id="8e908-115">기업 내부</span><span class="sxs-lookup"><span data-stu-id="8e908-115">Inside the enterprise.</span></span></p>
<p><span data-ttu-id="8e908-116">이 방법을 사용 하는 경우 감시자 노드는 모니터링 되는 풀과 같은 도메인에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e908-116">Note that, with this method, the watcher node must be in the same domain as the pools being monitored.</span></span> <span data-ttu-id="8e908-117">감시자 노드와 모니터링 되는 풀이 서로 다른 도메인에 있는 경우 자격 증명 인증을 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e908-117">If the watcher node and the monitored pools are in different domains, use Credential Authentication instead.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e908-118">자격 증명 인증</span><span class="sxs-lookup"><span data-stu-id="8e908-118">Credential Authentication</span></span></p></td>
<td><p><span data-ttu-id="8e908-119">각 감시자 노드의 Windows 자격 증명 관리자에 사용자 이름과 암호를 안전 하 게 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e908-119">Stores user names and passwords securely in Windows Credential Manager on each watcher node.</span></span></p>
<p><span data-ttu-id="8e908-120">이 모드를 사용 하는 경우에는 더 많은 암호 관리가 필요 하지만 기업 외부에 있는 감시자 노드에 대해서만 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e908-120">This mode requires more password management, but is the only option for watcher nodes located outside of the enterprise.</span></span> <span data-ttu-id="8e908-121">이러한 감시자 노드는 인증에 대해 신뢰할 수 있는 끝점으로 취급할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8e908-121">These watcher nodes cannot be treated as an endpoint trusted for authentication.</span></span></p></td>
<td><p><span data-ttu-id="8e908-122">기업 외부</span><span class="sxs-lookup"><span data-stu-id="8e908-122">Outside the enterprise.</span></span></p>
<p><span data-ttu-id="8e908-123">기업 내부</span><span class="sxs-lookup"><span data-stu-id="8e908-123">Inside the enterprise.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8e908-124">또한 방화벽에 MonitoringHost.exe 및 PowerShell.exe에 대 한 인바운드 규칙이 있는지도 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e908-124">You should also verify that your firewall has inbound rules for both MonitoringHost.exe and PowerShell.exe.</span></span> <span data-ttu-id="8e908-125">이러한 프로세스가 방화벽에 의해 차단 되 면 가상 트랜잭션이 504 (서버 시간 제한) 오류로 인해 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e908-125">If these processes are blocked by the firewall then your synthetic transactions will fail with a 504 (server timeout) error.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

