---
title: 'Lync Server 2013: 공용 메신저 연결 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 871f513170fcb0491f6732751cfc1b23877526b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="bd9cc-102">Lync Server 2013에서 공용 메신저 연결 설정</span><span class="sxs-lookup"><span data-stu-id="bd9cc-102">Setting up public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd9cc-103">_**마지막으로 수정한 주제:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="bd9cc-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="bd9cc-104">조직에서 AOL과 공용 인스턴트 메시징 (IM) 연결을 지원 하려는 경우 Lync Server 배포 마법사를 사용 하 여 인증서를 요청할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bd9cc-104">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate.</span></span> <span data-ttu-id="bd9cc-105">대신 다음 절차의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9cc-105">Instead, perform the steps in the following procedure.</span></span>

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a><span data-ttu-id="bd9cc-106">공용 인스턴트 메시지 연결 설정</span><span class="sxs-lookup"><span data-stu-id="bd9cc-106">Setting Up Public Instant Messaging Connectivity</span></span>

1.  <span data-ttu-id="bd9cc-107">프런트 엔드 서버에서 토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bd9cc-107">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="bd9cc-108">Edge 풀을 확장 한 다음 Edge 서버 또는 Edge 서버 풀을 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9cc-108">Expand Edge pools, then right click your Edge server or Edge server pool.</span></span> <span data-ttu-id="bd9cc-109">속성 편집을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9cc-109">Select Edit properties.</span></span>

2.  <span data-ttu-id="bd9cc-110">일반 아래에서 속성 편집에서이 Edge 풀에 페더레이션 사용 (포트 5061)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9cc-110">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061).</span></span> <span data-ttu-id="bd9cc-111">확인을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9cc-111">Click OK.</span></span>

3.  <span data-ttu-id="bd9cc-112">작업을 클릭 하 고 토폴로지를 선택한 다음 게시를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9cc-112">Click Action, select Topology, select Publish.</span></span> <span data-ttu-id="bd9cc-113">토폴로지를 게시할 것인지 묻는 메시지가 표시 되 면 다음을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9cc-113">When prompted on Publish the topology, click Next.</span></span> <span data-ttu-id="bd9cc-114">게시가 완료 되 면 마침을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9cc-114">When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="bd9cc-115">Edge 서버에서 Lync Server 배포 마법사를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bd9cc-115">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="bd9cc-116">Lync Server 시스템 설치 또는 업데이트를 클릭 한 다음 설정 또는 Lync Server 구성 요소 제거를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9cc-116">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="bd9cc-117">다시 실행을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9cc-117">Click Run Again.</span></span>

5.  <span data-ttu-id="bd9cc-118">Lync Server 구성 요소를 설정 하 고 다음을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9cc-118">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="bd9cc-119">요약 화면에 실행 되는 작업이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd9cc-119">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="bd9cc-120">배포가 완료 되 면 로그 보기를 클릭 하 여 사용 가능한 로그 파일을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="bd9cc-120">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="bd9cc-121">마침을 클릭 하 여 배포를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9cc-121">Click Finish to complete the deployment.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="bd9cc-122">AOL과 공용 IM 연결을 지원 하기 위해 Edge 서버의 외부 인터페이스에 대 한 인증서 요청을 만들려면</span><span class="sxs-lookup"><span data-stu-id="bd9cc-122">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="bd9cc-123">CA에서 필요한 템플릿을 사용할 수 있는 경우 Edge 서버에서 다음 Windows PowerShell cmdlet을 사용 하 여 인증서를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9cc-123">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="bd9cc-124">Lync Server에 사용 되는 서식 파일의 기본 인증서 이름은 웹 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="bd9cc-124">The default certificate name of the template used for Lync Server is Web Server.</span></span> <span data-ttu-id="bd9cc-125">기본 서식 파일과 \<다른 서식\> 파일을 사용 해야 하는 경우에만 서식 파일 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9cc-125">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bd9cc-126">조직에서 AOL과 공용 IM 연결을 지원 하려는 경우 인증서 마법사 대신 Windows PowerShell을 사용 하 여 액세스에 지 서비스의 외부에 지에 할당할 인증서를 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9cc-126">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="bd9cc-127">이는 인증서 마법사가 인증서를 요청 하는 데 사용 하는 CA (인증 기관) 웹 서버 템플릿이 클라이언트 EKU 구성을 지원 하지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="bd9cc-127">This is because the Certificate Authority (CA) Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="bd9cc-128">Windows PowerShell을 사용 하 여 인증서를 만들려면 먼저 CA 관리자가 클라이언트 EKU를 지 원하는 새 템플릿을 만들고 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9cc-128">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

