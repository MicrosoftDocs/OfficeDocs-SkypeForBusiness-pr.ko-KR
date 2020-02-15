---
title: 'Lync Server 2013: 장치 업데이트 규칙'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update rules
ms:assetid: a2f7e293-3342-4566-9605-410cb95f3b3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994062(v=OCS.15)
ms:contentKeyID: 51803973
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b52fa2f2aefae05f713972df5c3b15e6db7c0b57
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-rules-in-lync-server-2013"></a><span data-ttu-id="03ef1-102">Lync Server 2013의 장치 업데이트 규칙</span><span class="sxs-lookup"><span data-stu-id="03ef1-102">Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03ef1-103">_**마지막으로 수정 된 항목:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="03ef1-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="03ef1-104">Microsoft는 주기적으로 Lync Phone Edition에 대 한 새로운 장치 펌웨어 업데이트 집합을 출시 합니다.</span><span class="sxs-lookup"><span data-stu-id="03ef1-104">Periodically, Microsoft releases a new set of device firmware updates for Lync Phone Edition.</span></span> <span data-ttu-id="03ef1-105">*장치 업데이트 규칙* 은 펌웨어 업데이트를 하드웨어 장치 (Lync Phone Edition을 실행 하는 전화 및 기타 장치)와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="03ef1-105">*Device update rules* associate firmware updates with hardware devices—phones and other devices running Lync Phone Edition.</span></span>

<span data-ttu-id="03ef1-106">최신 장치 업데이트 규칙 집합을 가져오려면 Microsoft 웹 사이트의 도움말 및 지원 페이지로 이동 하 여 "Phone Edition"을 검색 하세요.</span><span class="sxs-lookup"><span data-stu-id="03ef1-106">To get the latest set of device update rules, go to the Help and Support page on the Microsoft website, and search for "Phone Edition."</span></span> <span data-ttu-id="03ef1-107">업데이트 패키지를 다운로드 하 고 업데이트를 업로드할 컴퓨터의 폴더에 파일 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="03ef1-107">Download the update package, and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="03ef1-108">파일의 압축을 푼 후에는 추출한 장치에서 찾은 디바이스 업데이트 규칙을 가져옵니다. CAB 파일 (cab 업데이트 .cab)을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="03ef1-108">After the files have been extracted, import the device update rules found in the extracted .CAB file (which have the name UCUpdates.cab).</span></span> <span data-ttu-id="03ef1-109">그런 다음 Lync Server 제어판 또는 Windows PowerShell cmdlet을 사용 하 여 조직의 장치에 대 한 이러한 규칙을 보고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="03ef1-109">Then, use the Lync Server Control Panel or Windows PowerShell cmdlets to view and manage these rules for your organization’s devices.</span></span>

<span data-ttu-id="03ef1-110">다음 항목에서는 장치 업데이트 규칙을 가져오고, 보고, 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="03ef1-110">The following topics tell you how to import, view, and manage device update rules.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="03ef1-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="03ef1-111">In This Section</span></span>

  - [<span data-ttu-id="03ef1-112">Lync Server 2013의 장치 업데이트 규칙에 대 한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="03ef1-112">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)

  - [<span data-ttu-id="03ef1-113">Lync Server 2013에서 장치 업데이트 규칙 가져오기</span><span class="sxs-lookup"><span data-stu-id="03ef1-113">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)

  - [<span data-ttu-id="03ef1-114">Lync Server 2013에서 장치 업데이트 규칙 승인</span><span class="sxs-lookup"><span data-stu-id="03ef1-114">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)

  - [<span data-ttu-id="03ef1-115">Lync Server 2013에서 장치 업데이트 규칙 제거</span><span class="sxs-lookup"><span data-stu-id="03ef1-115">Remove a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-remove-a-device-update-rule.md)

  - [<span data-ttu-id="03ef1-116">Lync Server 2013에서 장치 업데이트 규칙 다시 설정</span><span class="sxs-lookup"><span data-stu-id="03ef1-116">Reset a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-reset-a-device-update-rule.md)

  - [<span data-ttu-id="03ef1-117">Lync Server 2013에서 장치 업데이트 규칙 복원</span><span class="sxs-lookup"><span data-stu-id="03ef1-117">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

