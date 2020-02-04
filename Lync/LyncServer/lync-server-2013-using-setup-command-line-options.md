---
title: 'Lync Server 2013: 설치 명령줄 옵션 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fcf3637ac0d334c2d22ef714891ea0544ee1a6d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-setup-command-line-options-in-lync-server-2013"></a><span data-ttu-id="d7708-102">Lync Server 2013에서 설치 명령줄 옵션 사용</span><span class="sxs-lookup"><span data-stu-id="d7708-102">Using Setup command-line options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7708-103">_**마지막으로 수정한 주제:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="d7708-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="d7708-104">Setup.exe 명령줄은 Office 설치 프로그램의 매우 적은 작업에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7708-104">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="d7708-105">설치 명령줄 옵션을 사용 하는 대신 일반적으로 Office 사용자 지정 도구 및 Config .xml 파일을 사용 하 여 제품 설정 및 기능을 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7708-105">Instead of using the Setup command-line options, you’ll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>

<span data-ttu-id="d7708-106">Office Setup.exe 명령줄은 다음 표에 설명 된 명령줄 옵션을 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7708-106">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>

### <a name="office-setup-command-line-options"></a><span data-ttu-id="d7708-107">Office 설치 명령줄 옵션</span><span class="sxs-lookup"><span data-stu-id="d7708-107">Office Setup Command-Line Options</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7708-108">설치 명령줄 옵션</span><span class="sxs-lookup"><span data-stu-id="d7708-108">Setup Command-Line Option</span></span></th>
<th><span data-ttu-id="d7708-109">설명</span><span class="sxs-lookup"><span data-stu-id="d7708-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7708-110">/admin</span><span class="sxs-lookup"><span data-stu-id="d7708-110">/admin</span></span></p></td>
<td><p><span data-ttu-id="d7708-111">Office 사용자 지정 도구를 실행 하 여 설치 사용자 지정 파일 (.msp 파일)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d7708-111">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7708-112">/adminfile [path]</span><span class="sxs-lookup"><span data-stu-id="d7708-112">/adminfile [path]</span></span></p></td>
<td><p><span data-ttu-id="d7708-113">설치에 지정 된 설치 사용자 지정 파일을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7708-113">Applies the specified Setup customization file to the installation.</span></span> <span data-ttu-id="d7708-114">특정 사용자 지정 파일 (.msp 파일) 또는 사용자 지정 파일을 저장 하는 폴더에 대 한 경로를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7708-114">You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7708-115">/config [path]</span><span class="sxs-lookup"><span data-stu-id="d7708-115">/config [path]</span></span></p></td>
<td><p><span data-ttu-id="d7708-116">설치 중에 설치 하는 Config.xml 파일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7708-116">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="d7708-117">/Config 옵션을 사용 하 여 Lync 2013 설치에 대해 사용자 지정 된 Config.xml 파일을 지정 합니다 예:<code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span><span class="sxs-lookup"><span data-stu-id="d7708-117">Use the /config option to specify the Config.xml file you customized for Lync 2013 installations, for example: <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7708-118">/b Lync 수정</span><span class="sxs-lookup"><span data-stu-id="d7708-118">/modify Lync</span></span></p></td>
<td><p><span data-ttu-id="d7708-119">수정 된 Config.xml 파일을 사용 하 여 유지 관리 모드에서 설치 프로그램을 실행 하 고 기존 Office 설치를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7708-119">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="d7708-120">예를 들어/수정 옵션을 사용 하 여 Lync 기능을 추가 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7708-120">For example, you can use the /modify option to add or remove Lync features.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7708-121">/repair Lync</span><span class="sxs-lookup"><span data-stu-id="d7708-121">/repair Lync</span></span></p></td>
<td><p><span data-ttu-id="d7708-122">사용자 컴퓨터에서 설치 프로그램을 실행 하 여 Lync를 복구 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7708-122">Runs Setup from the user’s computer to repair Lync.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7708-123">/uninstall Lync</span><span class="sxs-lookup"><span data-stu-id="d7708-123">/uninstall Lync</span></span></p></td>
<td><p><span data-ttu-id="d7708-124">설치 프로그램을 실행 하 여 사용자의 컴퓨터에서 Lync를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7708-124">Runs Setup to remove Lync from the user’s computer.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d7708-125">설치 명령줄 옵션을 사용 하는 방법에 대 한 자세한 <http://go.microsoft.com/fwlink/p/?linkid=267515>내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d7708-125">For details about using the setup command-line options, see <http://go.microsoft.com/fwlink/p/?linkid=267515>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

