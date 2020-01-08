---
title: 'Lync Server 2013: Lync VDI 플러그 인 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying the Lync VDI plug-in
ms:assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204683(v=OCS.15)
ms:contentKeyID: 48183449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77b2e7ce89fe021c23da81f075aec3d1ce90e7b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="44349-102">Lync Server 2013에서 Lync VDI 플러그 인 배포</span><span class="sxs-lookup"><span data-stu-id="44349-102">Deploying the Lync VDI plug-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44349-103">_**마지막으로 수정한 주제:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="44349-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="44349-104">Lync 2013 클라이언트는 VDI (가상 데스크톱 인프라) 환경에서 오디오 및 비디오를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="44349-104">The Lync 2013 client supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="44349-105">사용자는 오디오 또는 비디오 장치 (예: 헤드셋 또는 카메라)를 로컬 컴퓨터 (예: 씬 클라이언트 또는 컴퓨터 시스템)에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44349-105">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="44349-106">사용자는 가상 컴퓨터에 연결 하 고, 가상 컴퓨터에서 실행 중인 Lync 2013 클라이언트에 로그인 하 고, 클라이언트가 로컬로 실행 되는 것 처럼 실시간 오디오 및 비디오 통신에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44349-106">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communications as though the client is running locally.</span></span>

<span data-ttu-id="44349-107">Lync VDI 플러그 인은 로컬 컴퓨터에 설치 하는 독립 실행형 응용 프로그램으로, 가상 컴퓨터에서 실행 되는 Lync 2013 클라이언트에서 로컬 오디오 및 비디오 장치를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44349-107">The Lync VDI Plug-in is a stand-alone application that installs on the local computer and allows the use of local audio and video devices with the Lync 2013 client running on the virtual machine.</span></span> <span data-ttu-id="44349-108">플러그 인을 사용할 경우에는 로컬 컴퓨터에 Lync를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44349-108">The plug-in does not require Lync to be installed on the local computer.</span></span> <span data-ttu-id="44349-109">사용자가 가상 머신에서 실행 중인 Lync 2013 클라이언트에 로그인 한 후에는 Lync에서 사용자에 게 자신의 자격 증명을 다시 입력 하 여 로컬 컴퓨터에서 실행 되는 Lync VDI 플러그 인에 대 한 연결을 설정 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="44349-109">After the user signs in to the Lync 2013 client that is running on the virtual machine, Lync prompts the user to re-enter his or her credentials to establish a connection with the Lync VDI Plug-in that is running on the local computer.</span></span> <span data-ttu-id="44349-110">이 연결이 설정 되 면 사용자는 음성 및 영상 통화를 설정 하 고 수신할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="44349-110">After this connection is established, the user is ready to make and receive audio and video calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="44349-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="44349-111">In This Section</span></span>

  - [<span data-ttu-id="44349-112">Lync Server 2013의 Lync VDI 플러그 인 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="44349-112">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>](lync-server-2013-lync-vdi-plug-in-prerequisites.md)

  - [<span data-ttu-id="44349-113">VDI에 대한 Lync Server 2013 환경 준비</span><span class="sxs-lookup"><span data-stu-id="44349-113">Preparing your Lync Server 2013 environment for VDI</span></span>](lync-server-2013-preparing-your-environment-for-vdi.md)

  - [<span data-ttu-id="44349-114">가상 컴퓨터에서 Lync 2013 로그인 및 사용</span><span class="sxs-lookup"><span data-stu-id="44349-114">Signing in and using Lync 2013 on the virtual machine</span></span>](lync-server-2013-signing-in-and-using-lync-2013-on-the-virtual-machine.md)

  - [<span data-ttu-id="44349-115">Lync Server 2013에서 Lync VDI 플러그 인 문제 해결</span><span class="sxs-lookup"><span data-stu-id="44349-115">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-the-lync-vdi-plug-in.md)

  - [<span data-ttu-id="44349-116">Lync Server 2013의 지원되는 가상화 기술 및 알려진 제한 사항</span><span class="sxs-lookup"><span data-stu-id="44349-116">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>](lync-server-2013-supported-virtualization-technologies-and-known-limitations.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

