---
title: 로컬 구성 저장소 설치
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: 새 비즈니스용 Skype 서버 역할 서버의 설치를 시작하려면 먼저 로컬 구성 저장소를 호스팅할 SQL Server 로컬 서버를 설치해야 합니다. 로컬 구성 저장소는 비즈니스용 Skype 서버 CMS(중앙 관리 저장소)의 읽기 전용 복제본 역할을 합니다.
ms.openlocfilehash: dcaf00e0bd14daecb6d2859bf40463265a3d6bc6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833808"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="b1837-104">로컬 구성 저장소 설치</span><span class="sxs-lookup"><span data-stu-id="b1837-104">Install Local Configuration Store</span></span>

<span data-ttu-id="b1837-105">새 비즈니스용 Skype 서버 역할 서버의 설치를 시작하려면 먼저 로컬 구성 저장소를 호스팅할 SQL Server 로컬 서버를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1837-105">To begin the installation of a new Skype for Business Server role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="b1837-106">로컬 구성 저장소는 비즈니스용 Skype 서버 CMS(중앙 관리 저장소)의 읽기 전용 복제본 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1837-106">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="b1837-107">컴퓨터의 로컬 관리자로 **로컬 구성 저장소 설치** 단계를 실행 중인 서버에 로그온하고 RTCUniversalServerAdmins 또는 RTCUniversalGlobalReadOnlyGroup 그룹의 구성원 자격을 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1837-107">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="b1837-108">에지 서버에서 설치를 수행 중인 경우 RTCUniversalServerAdmins 또는 RTCUniversalGlobalReadOnlyGroup 그룹의 구성원일 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b1837-108">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="b1837-109">토폴로지 작성기 정의 문서는 중앙 관리 저장소가 아닌 내보낼 정의 문서에서 읽어 들이게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1837-109">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="b1837-110">토폴로지 작성기 정의 문서를 내보내고 에지 서버에서 사용할 수 있도록 설정하기 위해 토폴로지 내보내기 및 에지 설치를 위해 외부 미디어에 토폴로지 복사 항목을[참조하세요.](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx)</span><span class="sxs-lookup"><span data-stu-id="b1837-110">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic[Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="b1837-111">설치를 시작하려면</span><span class="sxs-lookup"><span data-stu-id="b1837-111">To begin the installation:</span></span>

1. <span data-ttu-id="b1837-112">1단계: 로컬 구성 저장소 설치 옆의 비즈니스용 Skype 서버 페이지에서 실행을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b1837-112">On the Skype for Business Server page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="b1837-113">**로컬 서버 구성** 페이지에서 **중앙 관리 저장소의 구성 자동 검색** 옵션이 선택되어 있는지 확인하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1837-113">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="b1837-114">로컬 서버 구성 설치가 완료되면 **마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1837-114">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="b1837-115">로컬 로컬 설치 SQL Server 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1837-115">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="b1837-116">설치가 진행되는 동안에는 설치 요약 화면에서 업데이트가 SQL Server 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1837-116">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="b1837-117">설치 진행률을 모니터링하려면 작업 관리자를 사용하여 설치 SQL Server 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1837-117">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>


