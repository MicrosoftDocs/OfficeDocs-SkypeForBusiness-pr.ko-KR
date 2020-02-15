---
title: 'Lync Server 2013: 모니터링할 Lync Server 컴퓨터 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computers that will be monitored
ms:assetid: 9f1b2b91-d5af-42ad-a27d-b0815f762ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205118(v=OCS.15)
ms:contentKeyID: 48184927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0568f13cb977fad78e8d0e704c158039165ea78a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-computers-that-will-be-monitored-in-lync-server-2013"></a><span data-ttu-id="60765-102">Lync Server 2013에서 모니터링할 Lync Server 컴퓨터 구성</span><span class="sxs-lookup"><span data-stu-id="60765-102">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60765-103">_**마지막으로 수정 된 항목:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="60765-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="60765-104">Lync Server 2013에서는 Microsoft Lync Server 2010에서 사용 되는 중앙 검색 프로세스를 사용 하지 않으므로 모니터링 하려는 각 Lync Server 2013 컴퓨터는 관리 서버에 대 한 존재 여부를 자체 보고할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60765-104">Because Lync Server 2013 does not use the central discovery process used in Microsoft Lync Server 2010, each Lync Server 2013 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="60765-105">이를 위해서는 모니터링할 각 컴퓨터에 Operations Manager 에이전트 파일을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60765-105">To make this possible, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="60765-106">에이전트 파일을 설치한 후에는 컴퓨터가 System Center 프록시로 작동하도록 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60765-106">After the agent files have been installed, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="60765-107">이러한 절차는 이러한 컴퓨터에 Lync Server를 설치 및 구성한 후에 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60765-107">Note that these procedures should be carried out after you have installed and configured Lync Server on these computers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

