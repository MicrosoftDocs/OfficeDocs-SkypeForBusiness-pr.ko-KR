---
title: 'Lync Server 2013: 토폴로지 작성기에서 토폴로지 정의 및 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a topology in Topology Builder
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398788(v=OCS.15)
ms:contentKeyID: 48184953
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 597f331ba95ee563155fdabc6b95d35367d12080
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a><span data-ttu-id="8bd49-102">Lync Server 2013에 대 한 토폴로지 작성기에서 토폴로지 정의 및 구성</span><span class="sxs-lookup"><span data-stu-id="8bd49-102">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bd49-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="8bd49-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="8bd49-104">토폴로지 작성기를 실행 하 여 새 토폴로지를 정의 하거나 기존 토폴로지를 수정 하는 경우 로컬 관리자 또는 권한 있는 도메인 그룹의 구성원 자격은 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bd49-104">Running Topology Builder to define a new topology or to modify an existing topology does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="8bd49-105">토폴로지 작성기는 구성 요구 사항에 따라 Enterprise Edition 프런트 엔드 풀 또는 Standard Edition에 대 한 토폴로지를 정의 하는 데 필요한 단계를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd49-105">Topology Builder guides you through the steps necessary to define your topology for an Enterprise Edition Front End pool or a Standard Edition, based on your configuration requirements.</span></span>

<span data-ttu-id="8bd49-106">서버에 Lync Server 2013을 설치 하려면 토폴로지 작성기를 사용 하 여 토폴로지를 완료 하 고 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd49-106">You must use Topology Builder to complete and publish the topology before you can install Lync Server 2013 on servers.</span></span> <span data-ttu-id="8bd49-107">다음 절차에는 새 토폴로지를 정의하는 데 필요한 단계가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bd49-107">The following procedure includes the steps required to define a new topology.</span></span>

<div>

## <a name="to-define-a-topology"></a><span data-ttu-id="8bd49-108">토폴로지를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="8bd49-108">To define a topology</span></span>

1.  <span data-ttu-id="8bd49-109">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd49-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="8bd49-110">토폴로지 작성기에서 **새 토폴로지**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd49-110">In Topology Builder, select **New Topology**.</span></span> <span data-ttu-id="8bd49-111">토폴로지를 저장하기 위한 위치 및 파일 이름을 입력하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bd49-111">You are prompted for a location and file name for saving the topology.</span></span> <span data-ttu-id="8bd49-112">토폴로지 파일에 알기 쉬운 이름을 지정하고 기본 확장명 .tbxml을 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd49-112">Give the topology file a meaningful name and accept the default extension of .tbxml.</span></span> <span data-ttu-id="8bd49-113">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd49-113">Click **OK**.</span></span>

3.  <span data-ttu-id="8bd49-114">새 토폴로지 XML 파일을 저장할 위치로 이동하고 파일 이름을 입력한 다음 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd49-114">Navigate to the location where you want to save the new topology XML file, enter a name for the file, and then click **Save**.</span></span>

4.  <span data-ttu-id="8bd49-115">**주 도메인 정의** 페이지에서 조직의 주 SIP 도메인 이름을 입력한 다음 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd49-115">On the **Define the primary domain** page, enter the name of the primary SIP domain for your organization, and then click **Next**.</span></span>

5.  <span data-ttu-id="8bd49-116">**추가 지원 도메인 지정** 페이지에서 추가 도메인 이름을 입력한 다음(있는 경우) **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd49-116">On the **Specify additional supported domains** page, enter the names of additional domains, if any, and then click **Next**.</span></span>

6.  <span data-ttu-id="8bd49-117">**첫 번째 사이트 정의** 페이지에서 첫 번째 사이트의 이름과 설명을 입력한 다음 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd49-117">On the **Define the first site** page, enter a name and a description for the first site, and then click **Next**.</span></span>

7.  <span data-ttu-id="8bd49-118">**사이트 정보 지정** 페이지에서 사이트의 위치 정보를 입력한 다음 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd49-118">On the **Specify site details** page, enter the location information for the site, and then click **Next**.</span></span>

8.  <span data-ttu-id="8bd49-119">**새 토폴로지가 정의 되었습니다** 페이지에서 **이 마법사를 닫을 때 새 프런트 엔드 마법사를 엽니다** 확인란이 선택 되어 있는지 확인 하 고 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd49-119">On the **New topology was successfully defined** page, make sure the **Open the New Front End Wizard when this wizard closes** check box is selected, and then click **Finish**.</span></span>

<span data-ttu-id="8bd49-120">토폴로지를 정의 하 고 저장 한 후에는 새 프런트 엔드 마법사를 사용 하 여 사이트에 대 한 프런트 엔드 풀 또는 Standard Edition 서버를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd49-120">After you’ve defined and saved the topology, use the New Front End Wizard to define a Front End pool or Standard Edition server for your site.</span></span> <span data-ttu-id="8bd49-121">자세한 내용은 [Lync server 2013에서 프런트 엔드 풀 또는 Standard Edition 서버 정의 및 구성을](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8bd49-121">For details, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

