---
title: 'Lync Server 2013: IIS 보호'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 711adaec00e37cbd826f8aabcadc45948548c3f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="protecting-iis-in-lync-server-2013"></a><span data-ttu-id="6d124-102">Lync Server 2013에서 IIS 보호</span><span class="sxs-lookup"><span data-stu-id="6d124-102">Protecting IIS in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d124-103">_**마지막으로 수정한 주제:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="6d124-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="6d124-104">Microsoft Office Communications Server 2007 및 Microsoft Office Communications Server 2007 R2에서 IIS (인터넷 정보 서비스)는 표준 사용자 계정으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d124-104">In Microsoft Office Communications Server 2007 and Microsoft Office Communications Server 2007 R2, Internet Information Services (IIS) ran under a standard user account.</span></span> <span data-ttu-id="6d124-105">이로 인해 문제가 발생할 수 있습니다. 암호를 만료 한 경우에는 진단 하기 어려운 문제 인 웹 서비스를 잃게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d124-105">This had the potential to cause issues: if that password expired you could lose your Web Services, an issue that was often difficult to diagnose.</span></span> <span data-ttu-id="6d124-106">암호 만료 문제를 방지 하기 위해 Microsoft Lync Server 2013에서는 IIS를 실행 하는 사이트의 모든 컴퓨터에 대 한 인증 보안 주체의 역할을 하는 컴퓨터 계정 (실제로 존재 하지 않는 컴퓨터)을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d124-106">To help avoid the issue of expiring passwords, Microsoft Lync Server 2013 enables you to create a computer account (for a computer that doesn’t actually exist) that can serve as the authentication principal for all the computers in a site that are running IIS.</span></span> <span data-ttu-id="6d124-107">이러한 계정은 Kerberos 인증 프로토콜을 사용 하므로 계정이 Kerberos 계정 이라고 하 고 새 인증 프로세스를 Kerberos 웹 인증 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d124-107">Because these accounts use the Kerberos authentication protocol, the accounts are referred to as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="6d124-108">이렇게 하면 단일 계정을 사용 하 여 모든 IIS 서버를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d124-108">This enables you to manage all your IIS servers by using a single account.</span></span>

<span data-ttu-id="6d124-109">이 인증 원칙에 따라 서버를 실행 하려면 먼저 새-Cxeercosaccount cmdlet을 사용 하 여 컴퓨터 계정을 만들어야 합니다. 이 계정은 하나 이상의 사이트에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d124-109">To run your servers under this authentication principal, you must first create a computer account by using the New-CsKerberosAccount cmdlet; this account is then assigned to one or more sites.</span></span> <span data-ttu-id="6d124-110">할당이 완료 되 면 CsTopology cmdlet을 실행 하 여 계정 및 Lync Server 2013 사이트 간의 연결을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d124-110">After the assignment has been made, the association between the account and the Lync Server 2013 site is enabled by running the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="6d124-111">그 중에는 AD DS (Active Directory 도메인 서비스)에 필수 SPN (서비스 사용자 이름)이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="6d124-111">Among other things, this creates the required service principal name (SPN) in Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="6d124-112">Spn은 클라이언트 응용 프로그램에서 특정 서비스를 찾을 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d124-112">SPNs provide a way for client applications to locate a particular service.</span></span> <span data-ttu-id="6d124-113">자세한 내용은 운영 설명서의 [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6d124-113">For details, see [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) in the Operations documentation.</span></span>

<div>

## <a name="best-practices"></a><span data-ttu-id="6d124-114">모범 사례</span><span class="sxs-lookup"><span data-stu-id="6d124-114">Best Practices</span></span>

<span data-ttu-id="6d124-115">IIS의 보안을 강화 하려면 IIS에 대 한 Kerberos 계정을 구현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6d124-115">To help increase security of IIS, we recommend that you implement a Kerberos account for IIS.</span></span> <span data-ttu-id="6d124-116">Kerberos 계정을 구현 하지 않으면 IIS는 표준 사용자 계정으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d124-116">If you do not implement a Kerberos account, IIS runs under a standard user account.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

