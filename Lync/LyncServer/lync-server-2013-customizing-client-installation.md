---
title: 'Lync Server 2013: 클라이언트 설치 사용자 지정'
description: 'Lync Server 2013: 클라이언트 설치를 사용자 지정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Customizing client installation
ms:assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204934(v=OCS.15)
ms:contentKeyID: 48184254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8dd1942c298ccbc8b6a2950baf4f24cc2f797a92
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561144"
---
# <a name="customizing-client-installation-in-lync-server-2013"></a><span data-ttu-id="e2ab0-103">Lync Server 2013에서 클라이언트 설치 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="e2ab0-103">Customizing client installation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2ab0-104">_**마지막으로 수정 된 항목:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="e2ab0-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="e2ab0-105">엔터프라이즈 관리자는이 섹션에서 설명 하는 방법을 사용 하 여 Office 2013 Windows Installer 기반 (.msi) 설치를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2ab0-105">Enterprise administrators can customize the Office 2013 Windows Installer-based (.msi) installation by using the methods discussed in this section.</span></span> <span data-ttu-id="e2ab0-106">단일 도구에서는 모든 사용자 지정 옵션을 제공 하지 않으므로 Lync 2013 배포에서 이러한 방법을 조합 하 여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2ab0-106">Because no single tool provides all customization options, you’ll likely use a combination of these methods in your Lync 2013 deployment.</span></span> <span data-ttu-id="e2ab0-107">최소한 다음 섹션에 설명된 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2ab0-107">At a minimum, you might use the tools described in the following sections:</span></span>

  - <span data-ttu-id="e2ab0-108">[Lync Server 2013의 OCT (Office 사용자 지정 도구)를 사용](lync-server-2013-using-the-office-customization-tool-oct.md) 하 여 lync 및 기타 Office 프로그램에 대 한 설치 옵션 및 기능을 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ab0-108">[Using the Office Customization Tool (OCT) in Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) to customize setup options and features for Lync and other Office programs.</span></span>

  - <span data-ttu-id="e2ab0-109">[Config.xml을 사용 하 여 Lync Server 2013의 설치 작업을 수행](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) 하 여 네트워크 설치 지점의 경로를 지정 하 고 자동 설치를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ab0-109">[Using Config.xml to perform installation tasks in Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>

  - <span data-ttu-id="e2ab0-110">[Lync Server 2013의 설치 명령줄 옵션을 사용 하 여](lync-server-2013-using-setup-command-line-options.md) 설치 중에 사용할 Config.xml 파일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2ab0-110">[Using Setup command-line options in Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>

  - <span data-ttu-id="e2ab0-111">그룹 정책 개체 편집기 MMC 스냅인을 사용 하 여 [Lync Server 2013에서 클라이언트 부트스트랩 정책 구성](lync-server-2013-configuring-client-bootstrapping-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e2ab0-111">[Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>

<span data-ttu-id="e2ab0-p102">Office 제품군을 배포할 때는 다른 옵션들을 구성해야 할 수 있습니다. 이 섹션의 항목에서는 이러한 사용자 지정 도구에 대한 개요를 제공하고 Lync 관련 고려 사항에 대해 설명합니다. 각 도구에 대한 자세한 Office 도움말 링크도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2ab0-p102">There will probably be other options you’ll want to configure as you deploy the Office suite of products. The topics in this section give an overview of these customization tools and discuss Lync-specific considerations. Included are links to detailed Office help for each tool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

