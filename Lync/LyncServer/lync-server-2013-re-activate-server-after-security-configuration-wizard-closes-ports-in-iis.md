---
title: 보안 구성 마법사가 IIS에서 포트를 닫은 후 서버 다시 활성화
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c939996c10c85141d3c3751ce84b0cf642007b9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a><span data-ttu-id="afd26-102">보안 구성 마법사가 IIS에서 포트를 닫은 후 서버 다시 활성화</span><span class="sxs-lookup"><span data-stu-id="afd26-102">Re-activate server after Security Configuration Wizard closes ports in IIS</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afd26-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="afd26-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="afd26-104">일부 Lync Server 2013 역할은 IIS (인터넷 정보 서비스) 포트 4443에서 웹 서비스를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd26-104">Some Lync Server 2013 roles run Web Services on Internet Information Services (IIS) port 4443.</span></span> <span data-ttu-id="afd26-105">Lync Server 배포 마법사 실행, 부트스트래퍼 또는 **Enable-CsComputer** cmdlet을 사용 하 여 방화벽에서 예외를 만들고 포트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="afd26-105">Running the Lync Server Deployment Wizard, Bootstrapper.exe, or using the **Enable-CsComputer** cmdlet creates an exception in the firewall and opens the port.</span></span> <span data-ttu-id="afd26-106">그런 다음 Windows Server 2008 R2 보안 구성 마법사 (또는 기타 강화 스크립트)를 실행 하면 포트 4443이 차단 되 고 외부 클라이언트가 웹 서비스에 연결할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="afd26-106">If you then run the Windows Server 2008 R2 Security Configuration Wizard (or other hardening scripts), port 4443 will be blocked, and external clients will not be able to contact Web Services.</span></span> <span data-ttu-id="afd26-107">포트를 다시 열려면 방화벽 예외를 직접 수정 하거나 서버를 다시 활성화 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="afd26-107">To reopen the port you can either modify the firewall exception directly or re-activate the server.</span></span>

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a><span data-ttu-id="afd26-108">배포 마법사를 사용 하 여 서버를 다시 활성화 하려면</span><span class="sxs-lookup"><span data-stu-id="afd26-108">To re-activate the server by using the Deployment Wizard</span></span>

1.  <span data-ttu-id="afd26-109">Lync Server 배포 마법사 페이지에서 **2 단계: Lync Server 구성 요소 설정 또는 제거**옆의 **실행** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd26-109">On the Lync Server Deployment Wizard page, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

2.  <span data-ttu-id="afd26-110">**Lync Server 구성 요소 설정** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd26-110">On **Setup Lync Server components** page, click **Next**.</span></span>

3.  <span data-ttu-id="afd26-111">**명령 실행** 페이지에서 작업 상태가 완료로 표시 되 면 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="afd26-111">On the **Executing Commands** page, when the task status is shown as completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="afd26-112">또한 부트스트래퍼가 나 <STRONG>-CsComputer</STRONG> 를 사용 하 여 서버를 다시 활성화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afd26-112">You can also use bootstrapper.exe or <STRONG>Enable-CsComputer</STRONG> to re-activate the server.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

