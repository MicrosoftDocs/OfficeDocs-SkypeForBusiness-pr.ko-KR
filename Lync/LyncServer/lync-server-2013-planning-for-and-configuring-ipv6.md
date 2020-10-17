---
title: 'Lync Server 2013: IPv6 계획 및 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for and configuring IPv6
ms:assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204624(v=OCS.15)
ms:contentKeyID: 48183236
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 055dcf8de1d1a5e06e04e9b57bf4ffb44ab5a98f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515145"
---
# <a name="planning-for-and-configuring-ipv6-in-lync-server-2013"></a><span data-ttu-id="e1349-102">Lync Server 2013의 IPv6 계획 및 구성</span><span class="sxs-lookup"><span data-stu-id="e1349-102">Planning for and configuring IPv6 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1349-103">_**마지막으로 수정 된 항목:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="e1349-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="e1349-104">Lync Server 2013에는 ip 버전 6 (IPv6) 주소에 대 한 지원이 포함 되어 있는데,이 주소를 계속 해 서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1349-104">Lync Server 2013 includes support for IP version 6 (IPv6) addresses, along with continued support of IP version 4 (IPv4) addresses.</span></span> <span data-ttu-id="e1349-105">IPv4 주소는 컴퓨터가 인터넷을 통해 통신할 수 있도록 하는 32비트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="e1349-105">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="e1349-106">전 세계의 장치 수가 증가 함에 따라 사용 가능한 IPv4 주소는 실행 되지 않습니다. 따라서 많은 새 장치가 IPv6 주소를 사용 하도록 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1349-106">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span> <span data-ttu-id="e1349-107">IPv6 주소는 IPv4 주소와 같은 기능을 수행하며 일부 추가 기능을 제공하지만, 32비트만 사용하는 대신 128비트도 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e1349-107">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="e1349-108">따라서 새로운 주소 집합이 매우 많이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1349-108">This provides not only a new set of addresses, but also a much larger number of them.</span></span> <span data-ttu-id="e1349-109">일반적인 IPv4 주소는 192.0.2.235와 같으며, IPv6 주소는 2001:0db8:85a3:0000:0000:8a2e:0370:7334와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e1349-109">A typical IPv4 address looks something like this: 192.0.2.235, whereas an IPv6 address looks like this: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span></span> <span data-ttu-id="e1349-110">IPv6 주소를 사용 하는 장치에 대 한 서식 및 기능을 변경 하려면 Lync Server 2013 설치에서 몇 가지 배포 및 구성 고려 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1349-110">The change in formatting and functionality for devices that use IPv6 addresses requires several deployment and configuration considerations in your Lync Server 2013 installation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e1349-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="e1349-111">In This Section</span></span>

  - [<span data-ttu-id="e1349-112">Lync Server 2013의 IP 주소 유형 개요</span><span class="sxs-lookup"><span data-stu-id="e1349-112">Overview of IP address types for Lync Server 2013</span></span>](lync-server-2013-overview-of-ip-address-types.md)

  - [<span data-ttu-id="e1349-113">Lync Server 2013의 i p v 6에 대 한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1349-113">Technical requirements for IPv6 in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-ipv6.md)

  - [<span data-ttu-id="e1349-114">Lync Server 2013의 i p v 6에 대 한 마이그레이션 및 동시 사용 고려 사항</span><span class="sxs-lookup"><span data-stu-id="e1349-114">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>](lync-server-2013-migration-and-coexistence-considerations-for-ipv6.md)

  - [<span data-ttu-id="e1349-115">Lync Server 2013에서 IP 주소 유형 구성</span><span class="sxs-lookup"><span data-stu-id="e1349-115">Configure IP address types in Lync Server 2013</span></span>](lync-server-2013-configure-ip-address-types.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

