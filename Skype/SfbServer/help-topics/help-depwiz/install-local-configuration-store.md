---
title: 로컬 구성 저장소 설치
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/13/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: 새 비즈니스용 Skype 서버 2015 역할 서버 설치를 시작 하려면 먼저 로컬 구성 저장소를 호스트할 로컬 SQL Server를 설치 해야 합니다. 로컬 구성 저장소는 비즈니스용 Skype Server 중앙 관리 저장소 (CMS)의 읽기 전용 복제본 역할을 합니다. 로컬 구성 저장소 설치 단계를 실행하는 서버에는 해당 컴퓨터의 로컬 관리자로 로그온되어 있어야 하며, RTCUniversalServerAdmins 또는 RTCUniversalGlobalReadOnlyGroup 그룹의 구성원 자격이 있어야 합니다. 에지 서버에서 설치를 수행하는 경우에는 RTCUniversalServerAdmins 또는 RTCUniversalGlobalReadOnlyGroup 그룹의 구성원일 필요가 없습니다. 토폴로지 작성기 정의 문서는 중앙 관리 저장소 대신 내보낸 정의 문서에서 읽어 집니다. Edge 서버에서 사용할 수 있도록 토폴로지 작성기 정의 문서를 내보내려면 사용자의 토폴로지 내보내기 및 Edge 설치를 위해 외부 미디어에 복사 항목을 참조 하세요.
ms.openlocfilehash: c3da29e6c9630b22e7ae947f9b23ab5dbeebd13c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197188"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="a831f-108">로컬 구성 저장소 설치</span><span class="sxs-lookup"><span data-stu-id="a831f-108">Install Local Configuration Store</span></span>

<span data-ttu-id="a831f-109">새 비즈니스용 Skype 서버 2015 역할 서버 설치를 시작 하려면 먼저 로컬 구성 저장소를 호스트할 로컬 SQL Server를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a831f-109">To begin the installation of a new Skype for Business Server 2015 role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="a831f-110">로컬 구성 저장소는 비즈니스용 Skype Server 중앙 관리 저장소 (CMS)의 읽기 전용 복제본 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="a831f-110">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="a831f-111">**로컬 구성 저장소 설치** 단계를 실행하는 서버에는 해당 컴퓨터의 로컬 관리자로 로그온되어 있어야 하며, RTCUniversalServerAdmins 또는 RTCUniversalGlobalReadOnlyGroup 그룹의 구성원 자격이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a831f-111">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="a831f-112">에지 서버에서 설치를 수행하는 경우에는 RTCUniversalServerAdmins 또는 RTCUniversalGlobalReadOnlyGroup 그룹의 구성원일 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a831f-112">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="a831f-113">토폴로지 작성기 정의 문서는 중앙 관리 저장소 대신 내보낸 정의 문서에서 읽어 집니다.</span><span class="sxs-lookup"><span data-stu-id="a831f-113">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="a831f-114">Edge 서버에서 사용할 수 있도록 토폴로지 작성기 정의 문서를 내보내려면 [사용자의 토폴로지 내보내기 및 Edge 설치를 위해 외부 미디어에 복사](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx)항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a831f-114">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic [Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="a831f-115">설치를 시작하려면</span><span class="sxs-lookup"><span data-stu-id="a831f-115">To begin the installation:</span></span>

1. <span data-ttu-id="a831f-116">비즈니스용 Skype Server 2015 페이지에서 **Step1: 로컬 구성 저장소 설치 아래**에서 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a831f-116">On the Skype for Business Server 2015 page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="a831f-117">**로컬 서버 구성** 페이지에서 **중앙 관리 저장소의 구성 자동 검색** 옵션이 선택되어 있는지 확인하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a831f-117">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="a831f-118">로컬 서버 구성 설치가 완료되면 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a831f-118">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="a831f-119">로컬 SQL Server의 설치에는 약간의 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a831f-119">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="a831f-120">SQL Server를 설치 하는 동안에는 설치 요약 화면에 진행 상황 업데이트가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a831f-120">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="a831f-121">설치 진행률을 모니터링 하려면 작업 관리자를 사용 하 여 SQL Server 설정을 시청 하세요.</span><span class="sxs-lookup"><span data-stu-id="a831f-121">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>


