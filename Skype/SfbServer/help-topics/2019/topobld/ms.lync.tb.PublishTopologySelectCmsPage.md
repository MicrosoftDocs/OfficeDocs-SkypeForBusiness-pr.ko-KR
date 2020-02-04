---
title: 토폴로지 게시 CMS 페이지 선택
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: 토폴로지 작성기를 사용 하 여 구성한 토폴로지를 게시 합니다. 프런트 엔드 서버 또는 프런트 엔드 풀이 중앙 관리 저장소 보관 역할을 맡을 목록에서 선택 하 라는 메시지가 표시 됩니다. 지정 된 시간에이 역할을 보유할 수 있는 프런트 엔드 서버 또는 프런트 엔드 풀은 하나만 있습니다.
ms.openlocfilehash: 9cecdc170934f7359597484e56299e2fe76499b9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41701673"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="8494a-105">토폴로지 게시 CMS 페이지 선택</span><span class="sxs-lookup"><span data-stu-id="8494a-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="8494a-106">토폴로지 작성기를 사용 하 여 구성한 토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8494a-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="8494a-107">프런트 엔드 서버 또는 프런트 엔드 풀이 중앙 관리 저장소 보관 역할을 맡을 목록에서 선택 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8494a-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="8494a-108">지정 된 시간에이 역할을 보유할 수 있는 프런트 엔드 서버 또는 프런트 엔드 풀은 하나만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8494a-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="8494a-109">중앙 관리 서버 정보</span><span class="sxs-lookup"><span data-stu-id="8494a-109">About the Central Management Server</span></span>
<span data-ttu-id="8494a-110">중앙 관리 서버는 중앙 관리 서버를 포함 하는 프런트 엔드 서버에서 데이터베이스의 읽기/쓰기 복사본을 보유 하 고 있는 단일 마스터/다중 복제 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="8494a-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="8494a-111">중앙 관리 서버를 포함 하는 프런트 엔드 서버를 포함 하 여 토폴로지의 각 컴퓨터에는 설치 하는 동안 컴퓨터에 설치 된 SQL Server 데이터베이스 (기본적으로 RTCLOCAL 이라는)의 중앙 관리 저장소 데이터에 대 한 읽기 전용 복사본이 있습니다. 배포가.</span><span class="sxs-lookup"><span data-stu-id="8494a-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="8494a-112">로컬 데이터베이스는 모든 컴퓨터에서 서비스로 실행 되는 Lync Server 복제본 복제기 에이전트를 통해 복제본 업데이트를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="8494a-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="8494a-113">중앙 관리 서버 및 로컬 복제본의 실제 데이터베이스 이름은 xds, xds .mdf 파일로 구성 되는 XDS입니다.</span><span class="sxs-lookup"><span data-stu-id="8494a-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="8494a-114">Active Directory 도메인 서비스의 SCP (서비스 제어 지점)에서 마스터 데이터베이스 위치를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="8494a-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="8494a-115">중앙 관리 서버를 사용 하 여 Lync Server를 관리 하 고 구성 하는 모든 도구는 SCP를 사용 하 여 중앙 관리 저장소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8494a-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8494a-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8494a-116">See also</span></span>

[<span data-ttu-id="8494a-117">이동-CsManagementServer</span><span class="sxs-lookup"><span data-stu-id="8494a-117">Move-CsManagementServer</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
