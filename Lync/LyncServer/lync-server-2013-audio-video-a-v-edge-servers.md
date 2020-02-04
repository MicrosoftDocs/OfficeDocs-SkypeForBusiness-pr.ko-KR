---
title: 'Lync Server 2013: 오디오/비디오 (A/V) Edge 서버'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c99cc3522c13ece937c6e2a0ba06f995431e08d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="16453-102">Lync Server 2013의 오디오/비디오 (A/V) Edge 서버</span><span class="sxs-lookup"><span data-stu-id="16453-102">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16453-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="16453-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="16453-104">A/V Edge 서비스는 내부 사용자 (조직의 네트워크에 로그온 한 사용자)가 외부 사용자 (조직의 네트워크에 로그인 하지 않은 사용자)와 오디오 및 비디오를 공유 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="16453-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="16453-105">A/V Edge 서비스는 오디오 및 비디오 외에도 데스크톱 공유 및 파일 전송에 대 한 지원도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="16453-105">In addition to audio and video, the A/V Edge service also provides support for such things desktop sharing and file transfer.</span></span>

<span data-ttu-id="16453-106">A/V Edge 서비스는 주로 A/V Edge 구성을 사용 하 여 관리 됩니다. 이러한 설정을 사용 하 여 포트당 사용자 당 할당할 최대 대역폭을 관리 하 고 해당 토큰을 갱신 하기 전에 인증 토큰을 사용할 수 있는 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="16453-106">The A/V Edge service is primarily managed by using A/V Edge configuration; these settings enable you to manage the maximum amount of bandwidth to be allocated per port and per user, and to specify the length of time that an authentication token can be used before that token must be renewed.</span></span> <span data-ttu-id="16453-107">A/V Edge 구성 설정을 사이트 또는 개별 A/V Edge 서버에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16453-107">A/V Edge configuration settings can be applied to sites or to individual A/V Edge servers.</span></span> <span data-ttu-id="16453-108">어떤 설정 모음에 우선 순위를 둘지를 결정 하는 경우 다음 가이드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="16453-108">When determining which collection of settings will take priority, use the following guide:</span></span>

  - <span data-ttu-id="16453-109">서비스 범위 (즉, 개별 서버)에 구성 된 설정은 모두에 게 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="16453-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="16453-110">사이트 범위에서 구성 된 설정은 전역 범위에서 구성 된 설정 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="16453-110">Settings configured at the site scope take priority over settings configured at the global scope.</span></span> <span data-ttu-id="16453-111">그러나 서비스 범위 설정 에서도 사이트 범위 설정이 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16453-111">However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="16453-112">전역 범위의 설정은 개별 서버에 구성 된 서비스 설정이 없고 해당 서버가 있는 사이트에 대 한 사이트 설정이 없는 경우에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16453-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="16453-113">A/V Edge 서비스는 Lync Server PowerShell 및 CsAVEdgeConfiguration cmdlet을 사용 하는 경우에만 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16453-113">The A/V Edge service can only be managed by using Lync Server PowerShell and the CsAVEdgeConfiguration cmdlets.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="16453-114">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="16453-114">In This Section</span></span>

  - [<span data-ttu-id="16453-115">Lync Server 2013에서 A/V Edge 서버 구성 정보 반환</span><span class="sxs-lookup"><span data-stu-id="16453-115">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [<span data-ttu-id="16453-116">Lync Server 2013에서 A/V Edge 서버 구성 설정 모음 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="16453-116">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [<span data-ttu-id="16453-117">Lync Server 2013에서 A/V Edge 서버 구성 설정의 기존 컬렉션 삭제</span><span class="sxs-lookup"><span data-stu-id="16453-117">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

