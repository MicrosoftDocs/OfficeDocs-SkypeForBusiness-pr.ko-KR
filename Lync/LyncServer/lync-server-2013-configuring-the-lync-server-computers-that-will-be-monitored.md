---
title: 'Lync Server 2013: 모니터링할 Lync Server 컴퓨터 구성'
description: 'Lync Server 2013: 모니터링할 Lync Server 컴퓨터를 구성 합니다.'
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
ms.openlocfilehash: 742bd8a67eb42472e598c45619514e9407cb29cf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556834"
---
# <a name="configuring-the-lync-server-computers-that-will-be-monitored-in-lync-server-2013"></a><span data-ttu-id="d275c-103">Lync Server 2013에서 모니터링할 Lync Server 컴퓨터 구성</span><span class="sxs-lookup"><span data-stu-id="d275c-103">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d275c-104">_**마지막으로 수정 된 항목:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="d275c-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="d275c-105">Lync Server 2013에서는 Microsoft Lync Server 2010에서 사용 되는 중앙 검색 프로세스를 사용 하지 않으므로 모니터링 하려는 각 Lync Server 2013 컴퓨터는 관리 서버에 대 한 존재 여부를 자체 보고할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d275c-105">Because Lync Server 2013 does not use the central discovery process used in Microsoft Lync Server 2010, each Lync Server 2013 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="d275c-106">이를 위해서는 모니터링할 각 컴퓨터에 Operations Manager 에이전트 파일을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d275c-106">To make this possible, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="d275c-107">에이전트 파일을 설치한 후에는 컴퓨터가 System Center 프록시로 작동하도록 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d275c-107">After the agent files have been installed, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="d275c-108">이러한 절차는 이러한 컴퓨터에 Lync Server를 설치 및 구성한 후에 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d275c-108">Note that these procedures should be carried out after you have installed and configured Lync Server on these computers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

