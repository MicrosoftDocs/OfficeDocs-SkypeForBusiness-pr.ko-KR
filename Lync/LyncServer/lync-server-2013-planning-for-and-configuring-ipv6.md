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
ms.openlocfilehash: 05ca3b20d78d20f4c442edcb3a5722700c3e14a5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-and-configuring-ipv6-in-lync-server-2013"></a><span data-ttu-id="e8222-102">Lync Server 2013에서 IPv6 계획 및 구성</span><span class="sxs-lookup"><span data-stu-id="e8222-102">Planning for and configuring IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8222-103">_**마지막으로 수정한 주제:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="e8222-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="e8222-104">Lync Server 2013에는 IPv4 (IP 버전 4) 주소에 대 한 지속적인 지원과 함께 IP 버전 6 (IPv6) 주소가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8222-104">Lync Server 2013 includes support for IP version 6 (IPv6) addresses, along with continued support of IP version 4 (IPv4) addresses.</span></span> <span data-ttu-id="e8222-105">IPv4 주소는 컴퓨터에서 인터넷을 통해 통신할 수 있도록 하는 32 비트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="e8222-105">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="e8222-106">전세계 장치 수가 증가 함에 따라 사용 가능한 IPv4 주소가 초과 되었습니다. 이 때문에 많은 새 장치가 IPv6 주소를 사용 하도록 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8222-106">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span> <span data-ttu-id="e8222-107">IPv6 주소는 IPv4 주소와 동일한 기능을 수행 하지만 (일부 추가 기능 포함), 32 비트만 사용 하는 대신 128 비트를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e8222-107">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="e8222-108">이렇게 하면 새 주소 집합 뿐만 아니라 훨씬 더 많은 수가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8222-108">This provides not only a new set of addresses, but also a much larger number of them.</span></span> <span data-ttu-id="e8222-109">일반적인 IPv4 주소는 다음과 같이 표시 됩니다. 192.0.2.235, IPv6 주소는 다음과 같습니다: 2001:0db8:85a3:0000:0000:8a2e: 0370:7334.</span><span class="sxs-lookup"><span data-stu-id="e8222-109">A typical IPv4 address looks something like this: 192.0.2.235, whereas an IPv6 address looks like this: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span></span> <span data-ttu-id="e8222-110">IPv6 주소를 사용 하는 디바이스의 서식 및 기능 변경에는 Lync Server 2013 설치에 몇 가지 배포 및 구성 고려 사항이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8222-110">The change in formatting and functionality for devices that use IPv6 addresses requires several deployment and configuration considerations in your Lync Server 2013 installation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e8222-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="e8222-111">In This Section</span></span>

  - [<span data-ttu-id="e8222-112">Lync Server 2013에 대한 IP 주소 유형의 개요</span><span class="sxs-lookup"><span data-stu-id="e8222-112">Overview of IP address types for Lync Server 2013</span></span>](lync-server-2013-overview-of-ip-address-types.md)

  - [<span data-ttu-id="e8222-113">Lync Server 2013의 IPv6에 대한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e8222-113">Technical requirements for IPv6 in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-ipv6.md)

  - [<span data-ttu-id="e8222-114">Lync Server 2013의 IPv6에 대한 마이그레이션 및 동시 사용 고려 사항</span><span class="sxs-lookup"><span data-stu-id="e8222-114">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>](lync-server-2013-migration-and-coexistence-considerations-for-ipv6.md)

  - [<span data-ttu-id="e8222-115">Lync Server 2013에서 IP 주소 유형 구성</span><span class="sxs-lookup"><span data-stu-id="e8222-115">Configure IP address types in Lync Server 2013</span></span>](lync-server-2013-configure-ip-address-types.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

