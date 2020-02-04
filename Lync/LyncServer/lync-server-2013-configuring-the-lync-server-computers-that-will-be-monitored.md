---
title: 'Lync Server 2013: 모니터링 하는 Lync Server 컴퓨터 구성'
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
ms.openlocfilehash: 68dccef2e9451e4c077f5292398bb663f1acb514
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734658"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-computers-that-will-be-monitored-in-lync-server-2013"></a><span data-ttu-id="c0ac5-102">Lync Server 2013에서 모니터링 되는 Lync Server 컴퓨터 구성</span><span class="sxs-lookup"><span data-stu-id="c0ac5-102">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0ac5-103">_**마지막으로 수정한 주제:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="c0ac5-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="c0ac5-104">Lync Server 2013에서 Microsoft Lync Server 2010에 사용 되는 중앙 검색 프로세스를 사용 하지 않기 때문에 모니터링할 각 Lync Server 2013 컴퓨터는 관리 서버에 대 한 존재 여부를 자체 보고할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ac5-104">Because Lync Server 2013 does not use the central discovery process used in Microsoft Lync Server 2010, each Lync Server 2013 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="c0ac5-105">이를 가능 하 게 하려면 모니터링할 각 컴퓨터에 Operations Manager 에이전트 파일을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ac5-105">To make this possible, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="c0ac5-106">에이전트 파일을 설치한 후에는 컴퓨터를 System Center 프록시로 작동 하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ac5-106">After the agent files have been installed, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="c0ac5-107">이러한 절차는 이러한 컴퓨터에 Lync Server를 설치 하 고 구성한 후에 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ac5-107">Note that these procedures should be carried out after you have installed and configured Lync Server on these computers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

