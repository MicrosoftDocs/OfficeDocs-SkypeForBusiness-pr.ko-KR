---
title: 'Lync Server 2013: 장치 업데이트 규칙'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device Update rules
ms:assetid: a2f7e293-3342-4566-9605-410cb95f3b3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994062(v=OCS.15)
ms:contentKeyID: 51803973
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cce4b0be575665d23b2b09126905fc35791f61ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985127"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-rules-in-lync-server-2013"></a><span data-ttu-id="8fbfc-102">Lync Server 2013의 장치 업데이트 규칙</span><span class="sxs-lookup"><span data-stu-id="8fbfc-102">Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fbfc-103">_**마지막으로 수정한 주제:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="8fbfc-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="8fbfc-104">Microsoft는 정기적으로 Lync Phone 에디션에 대 한 새로운 디바이스 펌웨어 업데이트 집합을 릴리스 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fbfc-104">Periodically, Microsoft releases a new set of device firmware updates for Lync Phone Edition.</span></span> <span data-ttu-id="8fbfc-105">*장치 업데이트 규칙* 은 펌웨어 업데이트를 하드웨어 장치 (Lync Phone Edition을 실행 하는 휴대폰 및 기타 장치)와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fbfc-105">*Device update rules* associate firmware updates with hardware devices—phones and other devices running Lync Phone Edition.</span></span>

<span data-ttu-id="8fbfc-106">최신 장치 업데이트 규칙 집합을 얻으려면 Microsoft 웹 사이트의 도움말 및 지원 페이지로 이동 하 여 "Phone Edition"을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fbfc-106">To get the latest set of device update rules, go to the Help and Support page on the Microsoft website, and search for "Phone Edition."</span></span> <span data-ttu-id="8fbfc-107">업데이트 패키지를 다운로드 하 고 업데이트를 업로드할 컴퓨터의 폴더에 파일 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="8fbfc-107">Download the update package, and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="8fbfc-108">파일의 압축을 푼 후에는 추출 된 장치에 있는 업데이트 규칙을 가져옵니다. CAB 파일 (.cab 업데이트 확장명)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fbfc-108">After the files have been extracted, import the device update rules found in the extracted .CAB file (which have the name UCUpdates.cab).</span></span> <span data-ttu-id="8fbfc-109">그런 다음 Lync Server 제어판 또는 Windows PowerShell cmdlet을 사용 하 여 조직의 디바이스에 대해 이러한 규칙을 보고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fbfc-109">Then, use the Lync Server Control Panel or Windows PowerShell cmdlets to view and manage these rules for your organization’s devices.</span></span>

<span data-ttu-id="8fbfc-110">다음 항목에서는 장치 업데이트 규칙을 가져오고, 보고, 관리 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fbfc-110">The following topics tell you how to import, view, and manage device update rules.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8fbfc-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="8fbfc-111">In This Section</span></span>

  - [<span data-ttu-id="8fbfc-112">Lync Server 2013에서 장치 업데이트 규칙에 대 한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="8fbfc-112">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)

  - [<span data-ttu-id="8fbfc-113">Lync Server 2013에서 장치 업데이트 규칙 가져오기</span><span class="sxs-lookup"><span data-stu-id="8fbfc-113">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)

  - [<span data-ttu-id="8fbfc-114">Lync Server 2013에서 장치 업데이트 규칙 승인</span><span class="sxs-lookup"><span data-stu-id="8fbfc-114">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)

  - [<span data-ttu-id="8fbfc-115">Lync Server 2013에서 장치 업데이트 규칙 제거</span><span class="sxs-lookup"><span data-stu-id="8fbfc-115">Remove a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-remove-a-device-update-rule.md)

  - [<span data-ttu-id="8fbfc-116">Lync Server 2013에서 장치 업데이트 규칙 다시 설정</span><span class="sxs-lookup"><span data-stu-id="8fbfc-116">Reset a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-reset-a-device-update-rule.md)

  - [<span data-ttu-id="8fbfc-117">Lync Server 2013에서 장치 업데이트 규칙 복원</span><span class="sxs-lookup"><span data-stu-id="8fbfc-117">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

