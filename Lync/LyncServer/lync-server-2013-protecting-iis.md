---
title: 'Lync Server 2013: IIS 보호'
description: 'Lync Server 2013: IIS 보호'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51161f221c7235aad04850fdccc5d5e9db5cb579
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579734"
---
# <a name="protecting-iis-in-lync-server-2013"></a><span data-ttu-id="583bc-103">Lync Server 2013에서 IIS 보호</span><span class="sxs-lookup"><span data-stu-id="583bc-103">Protecting IIS in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="583bc-104">_**마지막으로 수정 된 항목:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="583bc-104">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="583bc-105">Microsoft Office Communications Server 2007 및 Microsoft Office Communications Server 2007 R2에서는 IIS (인터넷 정보 서비스)가 표준 사용자 계정으로 실행 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="583bc-105">In Microsoft Office Communications Server 2007 and Microsoft Office Communications Server 2007 R2, Internet Information Services (IIS) ran under a standard user account.</span></span> <span data-ttu-id="583bc-106">이로 인해 문제가 발생할 가능성이 있었습니다. 암호가 만료 되 면 진단 하기 어려운 문제 인 웹 서비스가 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="583bc-106">This had the potential to cause issues: if that password expired you could lose your Web Services, an issue that was often difficult to diagnose.</span></span> <span data-ttu-id="583bc-107">암호 만료 문제를 방지 하기 위해 Microsoft Lync Server 2013에서는 IIS를 실행 하는 사이트의 모든 컴퓨터에 대 한 인증 사용자 역할을 할 수 있는 컴퓨터 계정 (실제로 존재 하지 않는 컴퓨터에 대 한)을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="583bc-107">To help avoid the issue of expiring passwords, Microsoft Lync Server 2013 enables you to create a computer account (for a computer that doesn’t actually exist) that can serve as the authentication principal for all the computers in a site that are running IIS.</span></span> <span data-ttu-id="583bc-108">이러한 계정은 Kerberos 인증 프로토콜을 사용 하기 때문에 계정을 Kerberos 계정 이라고 하며 새 인증 프로세스를 Kerberos 웹 인증 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="583bc-108">Because these accounts use the Kerberos authentication protocol, the accounts are referred to as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="583bc-109">이렇게 하면 단일 계정을 사용 하 여 모든 IIS 서버를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="583bc-109">This enables you to manage all your IIS servers by using a single account.</span></span>

<span data-ttu-id="583bc-110">이 인증 주체에서 서버를 실행 하려면 먼저 New-CsKerberosAccount cmdlet을 사용 하 여 컴퓨터 계정을 만들어야 합니다. 이 계정은 하나 이상의 사이트에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="583bc-110">To run your servers under this authentication principal, you must first create a computer account by using the New-CsKerberosAccount cmdlet; this account is then assigned to one or more sites.</span></span> <span data-ttu-id="583bc-111">할당을 수행한 후에는 Enable-CsTopology cmdlet을 실행 하 여 계정 및 Lync Server 2013 사이트 간의 연결이 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="583bc-111">After the assignment has been made, the association between the account and the Lync Server 2013 site is enabled by running the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="583bc-112">이렇게 하면 AD DS (Active Directory 도메인 서비스)에 필요한 SPN (서비스 사용자 이름)이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="583bc-112">Among other things, this creates the required service principal name (SPN) in Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="583bc-113">Spn은 클라이언트 응용 프로그램에서 특정 서비스를 찾을 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="583bc-113">SPNs provide a way for client applications to locate a particular service.</span></span> <span data-ttu-id="583bc-114">자세한 내용은 작업 설명서에서 [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="583bc-114">For details, see [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) in the Operations documentation.</span></span>

<div>

## <a name="best-practices"></a><span data-ttu-id="583bc-115">모범 사례</span><span class="sxs-lookup"><span data-stu-id="583bc-115">Best Practices</span></span>

<span data-ttu-id="583bc-116">IIS의 보안을 강화 하려면 IIS 용 Kerberos 계정을 구현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="583bc-116">To help increase security of IIS, we recommend that you implement a Kerberos account for IIS.</span></span> <span data-ttu-id="583bc-117">Kerberos 계정을 구현 하지 않으면 IIS가 표준 사용자 계정으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="583bc-117">If you do not implement a Kerberos account, IIS runs under a standard user account.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

