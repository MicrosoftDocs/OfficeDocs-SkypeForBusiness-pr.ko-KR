---
title: 기존 배포에서 토폴로지 다운로드
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19cf24e1ef287b50ffece7407913a7d2c45e7062
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755802"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="download-topology-from-existing-deployment"></a><span data-ttu-id="16d90-102">기존 배포에서 토폴로지 다운로드</span><span class="sxs-lookup"><span data-stu-id="16d90-102">Download topology from existing deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16d90-103">_**마지막으로 수정 된 항목:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="16d90-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="16d90-104">Lync Server 2013 풀을 만들 때는 Lync Server 2010와 연결 된 중앙 관리 저장소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="16d90-104">When creating a Lync Server 2013 pool, you will use the Central Management Store that is associated with Lync Server 2010.</span></span> <span data-ttu-id="16d90-105">최초 사용 시와 후속 편집 세션에서 토폴로지 작성기를 시작하면 토폴로지 작성기에서 현재 구성 문서를 로드할 위치를 선택하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="16d90-105">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="16d90-106">이미 Lync Server 2010 토폴로지가 정의 되어 있고 중앙 관리 저장소를 설정 했기 때문에 기존 배포에서 토폴로지를 다운로드 하도록 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16d90-106">Because you already have a Lync Server 2010 topology defined and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="16d90-107">그러면 토폴로지 작성기에서 데이터베이스를 읽고 현재 정의를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="16d90-107">Topology Builder will read the database and retrieve the current definition.</span></span>

<span data-ttu-id="16d90-108">**기존 배포에서 토폴로지를 다운로드하려면**</span><span class="sxs-lookup"><span data-stu-id="16d90-108">**To download a topology from an existing deployment**</span></span>

1.  <span data-ttu-id="16d90-109">**Lync Server 배포 마법사**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="16d90-109">Open the **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="16d90-110">**Lync Server 2013 – 배포 마법사** 페이지에서 **관리 도구 설치**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="16d90-110">From the **Lync Server 2013 – Deployment Wizard** page, click **Install Administrative Tools**.</span></span>

3.  <span data-ttu-id="16d90-111">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013** 을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16d90-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013** , and then click **Lync Server Topology Builder**.</span></span>

4.  <span data-ttu-id="16d90-112">**기존 배포에서 토폴로지 다운로드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="16d90-112">Select **Download Topology from existing deployment**.</span></span>
    
    <span data-ttu-id="16d90-113">![배포 마법사 토폴로지 작성기 설정](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "배포 마법사 토폴로지 작성기 설정")</span><span class="sxs-lookup"><span data-stu-id="16d90-113">![Deployment Wizard Topology Builder settings](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Deployment Wizard Topology Builder settings")</span></span>

5.  <span data-ttu-id="16d90-114">파일 이름을 선택하고 토폴로지를 기본 .tbxml 파일 형식으로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="16d90-114">Choose a file name and save the topology with the default .tbxml file type.</span></span>

6.  <span data-ttu-id="16d90-115">표시된 것처럼 Lync Server 노드를 확장하여 배포에 있는 다양한 서버 역할을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="16d90-115">Expand the Lync Server node, as shown, to reveal the various server roles in the deployment.</span></span>
    
    <span data-ttu-id="16d90-116">![토폴로지 작성기 서버 역할 일반 속성](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "토폴로지 작성기 서버 역할 일반 속성")</span><span class="sxs-lookup"><span data-stu-id="16d90-116">![Topology Builder server role general properties](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Topology Builder server role general properties")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

