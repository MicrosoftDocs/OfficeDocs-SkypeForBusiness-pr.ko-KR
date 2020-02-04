---
title: 'Lync Server 2013: Lync 2013에 대 한 그룹 정책 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Policy settings for Lync 2013
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204924(v=OCS.15)
ms:contentKeyID: 48184235
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3023741b1b9e71d7789857c9b55fb195453ee5b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="e141c-102">Lync 2013에 대 한 그룹 정책 설정</span><span class="sxs-lookup"><span data-stu-id="e141c-102">Group Policy settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e141c-103">_**마지막으로 수정한 주제:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="e141c-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="e141c-104">이전 버전의 Lync 및 Office Communicator에서 독립 실행형 Communicator 관리 템플릿은 클라이언트 그룹 정책 설정을 구성 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e141c-104">In previous versions of Lync and Office Communicator, a stand-alone Communicator.adm administrative template was available for configuring client Group Policy settings.</span></span> <span data-ttu-id="e141c-105">Lync 2013에는 Office 그룹 정책 관리 템플릿과 함께 새로운 관리 템플릿 파일 (admx 및 adml 파일이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e141c-105">For Lync 2013, new administrative template files (.admx and .adml files) are included along with the Office Group Policy Administrative Template.</span></span> <span data-ttu-id="e141c-106">Lync 2013. admx 및 adml 파일의 가용성을 통해 모든 Office 프로그램 및 언어 팩에 대 한 서식 파일을 다운로드 하 고 중앙에서 그룹 정책 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e141c-106">The availability of Lync 2013 .admx and .adml files allows you to download templates and centrally manage Group Policy settings for all your Office programs and language packs.</span></span> <span data-ttu-id="e141c-107">자세한 내용은 Office 2013 설명서에서 "Office 2013 관리 템플릿 파일 (ADMX, ADML)"을 참조 하세요 <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span><span class="sxs-lookup"><span data-stu-id="e141c-107">For details, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<div>

## <a name="client-bootstrapping-policies"></a><span data-ttu-id="e141c-108">클라이언트 부트스트랩 정책</span><span class="sxs-lookup"><span data-stu-id="e141c-108">Client Bootstrapping Policies</span></span>

<span data-ttu-id="e141c-109">사용자가 처음 서버에 로그인 하기 전에 구성 해야 하는 여러 가지 클라이언트 부트스트랩 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e141c-109">There are several client bootstrapping policies that you should configure before users sign in to the server for the first time.</span></span> <span data-ttu-id="e141c-110">이러한 정책은 클라이언트가 로그인 하 고 서버에서 대역내 프로비저닝 설정 수신을 시작 하기 전에 적용 되기 때문에 그룹 정책을 사용 하 여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e141c-110">Because these policies take effect before the client signs in and begins receiving in-band provisioning settings from the server, you can use Group Policy to configure them.</span></span> <span data-ttu-id="e141c-111">자세한 내용은 배포 설명서의 [Lync Server 2013에서 클라이언트 부트스트랩 정책 구성을](lync-server-2013-configuring-client-bootstrapping-policies.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e141c-111">For more information, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

