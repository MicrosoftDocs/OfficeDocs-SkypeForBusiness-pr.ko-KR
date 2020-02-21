---
title: 'Lync Server 2013: 영구 채팅 서버에 대 한 DNS 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Persistent Chat Servers
ms:assetid: f7531374-d7ed-4b63-ae81-02294cb4496a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205391(v=OCS.15)
ms:contentKeyID: 48185857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea581eb04f2899ecafd49364b38a1064303bdcdc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214334"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-persistent-chat-servers-in-lync-server-2013"></a><span data-ttu-id="1ef9c-102">Lync Server 2013의 영구 채팅 서버에 대 한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ef9c-102">DNS requirements for Persistent Chat Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ef9c-103">_**마지막으로 수정 된 항목:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="1ef9c-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="1ef9c-104">이 섹션에서는 영구 채팅 서버를 배포 하는 데 필요한 DNS (Domain Name System) 레코드에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ef9c-104">This section describes the Domain Name System (DNS) records that are required for deployment of Persistent Chat Servers.</span></span>

<div>

## <a name="dns-records-for-persistent-chat-servers"></a><span data-ttu-id="1ef9c-105">영구 채팅 서버에 대한 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="1ef9c-105">DNS Records for Persistent Chat Servers</span></span>

<span data-ttu-id="1ef9c-106">다음 표에서는 영구 채팅 서버 배포에 대 한 DNS 요구 사항을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ef9c-106">The following table specifies DNS requirements for Persistent Chat Server deployment.</span></span>

### <a name="dns-requirements-for-a-persistent-chat-server"></a><span data-ttu-id="1ef9c-107">영구 채팅 서버에 대한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ef9c-107">DNS Requirements for a Persistent Chat Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ef9c-108">배포 시나리오</span><span class="sxs-lookup"><span data-stu-id="1ef9c-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="1ef9c-109">DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ef9c-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ef9c-110">영구 채팅 서버 한 개</span><span class="sxs-lookup"><span data-stu-id="1ef9c-110">One Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="1ef9c-111">서버의 FQDN(정규화된 도메인 이름)을 IP 주소로 확인하는 내부 A 레코드</span><span class="sxs-lookup"><span data-stu-id="1ef9c-111">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ef9c-112">영구 채팅 풀</span><span class="sxs-lookup"><span data-stu-id="1ef9c-112">Persistent Chat pool</span></span></p></td>
<td><p><span data-ttu-id="1ef9c-113">서버의 FQDN(정규화된 도메인 이름)을 IP 주소로 확인하는 내부 A 레코드</span><span class="sxs-lookup"><span data-stu-id="1ef9c-113">An internal A record that resolves the fully qualified domain name (FQDN) of the servers to its IP address.</span></span></p>
<p><span data-ttu-id="1ef9c-114"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="1ef9c-114"><strong>Example</strong></span></span></p>
<p><span data-ttu-id="1ef9c-115">PersistentChatServer01.contoso.com 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="1ef9c-115">PersistentChatServer01.contoso.com     10.10.10.1</span></span></p>
<p><span data-ttu-id="1ef9c-116">PersistentChatServer02.contoso.com 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="1ef9c-116">PersistentChatServer02.contoso.com     10.10.10.2</span></span></p>
<p><span data-ttu-id="1ef9c-117">서버의 FQDN(정규화된 도메인 이름)을 IP 주소로 확인하는 내부 A 레코드</span><span class="sxs-lookup"><span data-stu-id="1ef9c-117">An internal A record that resolves the fully qualified domain name (FQDN) of the servers to its IP address.</span></span></p>
<p><span data-ttu-id="1ef9c-118"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="1ef9c-118"><strong>Example</strong></span></span></p>
<p><span data-ttu-id="1ef9c-119">PersistentChatPool.contoso.com 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="1ef9c-119">PersistentChatPool.contoso.com    10.10.10.1</span></span></p>
<p><span data-ttu-id="1ef9c-120">PersistentChatPool.contoso.com 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="1ef9c-120">PersistentChatPool.contoso.com    10.10.10.2</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

