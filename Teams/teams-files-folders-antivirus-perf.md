---
title: 바이러스 백신 검색에서 제외할 Teams 파일 및 폴더
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: 일반 바이러스 검사에서 특정 파일 및 폴더를 제외 하 여 팀의 성과를 향상 시킵니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c1519038cb2393687a031e9b2c1ea828f999728
ms.sourcegitcommit: bb88ac0c9489bb47957e5ef1074b5df3126b6fdb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/25/2020
ms.locfileid: "42265623"
---
<a name="teams-files-and-folders-to-exclude-from-antivirus-scanning"></a><span data-ttu-id="249e9-103">바이러스 백신 검색에서 제외할 Teams 파일 및 폴더</span><span class="sxs-lookup"><span data-stu-id="249e9-103">Teams files and folders to exclude from antivirus scanning</span></span>
=================================

<span data-ttu-id="249e9-104">바이러스 백신 프로그램이 특정 팀 파일 및 폴더를 검색 하지 못하도록 하 여 팀 배포의 전반적인 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="249e9-104">You can improve the overall performance of your Teams deployment by preventing your antivirus programs from scanning certain Teams files and folders.</span></span> <span data-ttu-id="249e9-105">이렇게 하면 검색할 필요가 없는 파일 및 폴더를 검색 하는 시스템 리소스의 비용을 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="249e9-105">This will avoid the expenditure of system resources on scanning files and folders that don't need to be scanned.</span></span>

> [!NOTE]
> <span data-ttu-id="249e9-106">사용자가 파일을 다운로드 하거나 파일을 공유 하는 경우, 해당 파일은 다음 섹션에 나열 된 위치를 통과 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="249e9-106">When your users download files or share files with each other, those files don't pass through the locations listed in the following section.</span></span> <span data-ttu-id="249e9-107">사용자가 업로드, 다운로드 또는 파일을 공유 하는 위치는 여전히 바이러스 백신 프로그램에서 정기적으로 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="249e9-107">The locations where your users do upload, download, or share files will still be regularly scanned by your antivirus program.</span></span>

## <a name="files-and-folders-to-add-to-your-antivirus-safe-lists"></a><span data-ttu-id="249e9-108">바이러스 백신 수신 허용 목록에 추가할 파일 및 폴더</span><span class="sxs-lookup"><span data-stu-id="249e9-108">Files and folders to add to your antivirus safe lists</span></span>

<span data-ttu-id="249e9-109">바이러스 백신 프로그램에서 지원 되는 절차를 사용 하 여 다음 파일 및 폴더를 수신 허용 목록에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="249e9-109">Use the procedures supported by your antivirus program to add the following files and folders to your safe lists.</span></span> <span data-ttu-id="249e9-110">이렇게 하면 이러한 위치에 대 한 바이러스 백신 검사를 방지 하 여 시스템 리소스를 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="249e9-110">Doing so will conserve system resources by avoiding antivirus scans of these locations.</span></span>

### <a name="programs"></a><span data-ttu-id="249e9-111">프로그램이</span><span class="sxs-lookup"><span data-stu-id="249e9-111">Programs</span></span>

<span data-ttu-id="249e9-112">바이러스 백신 수신 허용 목록에 다음 팀 프로그램을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="249e9-112">Add the following Teams programs to your antivirus safe list.</span></span>

<span data-ttu-id="249e9-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span><span class="sxs-lookup"><span data-stu-id="249e9-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span></span>

<span data-ttu-id="249e9-114">**%localappdata%\Microsoft\Teams\Update.exe**</span><span class="sxs-lookup"><span data-stu-id="249e9-114">**%localappdata%\Microsoft\Teams\Update.exe**</span></span>

### <a name="folders"></a><span data-ttu-id="249e9-115">폴더</span><span class="sxs-lookup"><span data-stu-id="249e9-115">Folders</span></span>

<span data-ttu-id="249e9-116">바이러스 백신 수신 허용 목록에 다음 팀 폴더를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="249e9-116">Add the following Teams folders to your antivirus safe list.</span></span>

|<span data-ttu-id="249e9-117">범주만</span><span class="sxs-lookup"><span data-stu-id="249e9-117">Category</span></span>  |<span data-ttu-id="249e9-118">위치</span><span class="sxs-lookup"><span data-stu-id="249e9-118">Location</span></span>  |
|---------|---------|
|<span data-ttu-id="249e9-119">프로그램 파일</span><span class="sxs-lookup"><span data-stu-id="249e9-119">Program files</span></span>  |<span data-ttu-id="249e9-120">%localappdata%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="249e9-120">%localappdata%\Microsoft\Teams</span></span>|
|<span data-ttu-id="249e9-121">데이터 파일</span><span class="sxs-lookup"><span data-stu-id="249e9-121">Data files</span></span>     |<span data-ttu-id="249e9-122">%appdata%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="249e9-122">%appdata%\Microsoft\Teams</span></span>\ |
