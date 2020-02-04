---
title: 'Lync Server 2013: 로컬 구성 저장소 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4af6d4b6dfe203f69a6b104b6ade636d2658178
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a><span data-ttu-id="836e0-102">Lync Server 2013에서 로컬 구성 저장소 설치</span><span class="sxs-lookup"><span data-stu-id="836e0-102">Install the Local Configuration store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="836e0-103">_**마지막으로 수정한 주제:** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="836e0-103">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="836e0-104">이 단계를 수행 하기 전에 로컬 관리자이 고 RTCUniversalReadOnlyAdmin 그룹의 구성원 인 도메인 사용자 계정을 사용 하 여 서버에 로그온 되어 있는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="836e0-104">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmin group.</span></span>

<span data-ttu-id="836e0-105">Lync Server 배포 마법사를 사용 하 여 모든 작업을 수행할 수 있으려면 서버에 로컬 구성 저장소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="836e0-105">To be able to do anything with the Lync Server Deployment Wizard, we need the Local Configuration store to exist on a server.</span></span> <span data-ttu-id="836e0-106">로컬 구성 저장소는 중앙 관리 저장소의 읽기 전용 복사본으로, SQL Server Express의 로컬 설치 이후 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="836e0-106">The Local Configuration store is a read-only copy of the Central Management store, which gets created after the local installation of SQL Server Express.</span></span> <span data-ttu-id="836e0-107">중앙 관리 저장소 자체는 Standard Edition server 또는 SQL Server Express 기반 데이터베이스에 설치 된 기존 SQL Server 데이터베이스에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="836e0-107">The Central Management store itself is added to the existing SQL Server database installed on the Standard Edition server or SQL Server Express-based database.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="836e0-108">이전에이 서버에서 Lync Server 2013 설치 프로그램을 실행 하지 않은 경우에는 Lync Server 2013를 설치할 드라이브와 경로를 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="836e0-108">If you haven’t run Lync Server 2013 setup on this server before, you’ll be prompted for a drive and path to install Lync Server 2013 to.</span></span> <span data-ttu-id="836e0-109">이렇게 하면 조직에 필요한 경우 시스템 드라이브 이외의 드라이브에 설치 하거나 공간에 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="836e0-109">This will let you install to a drive other than the system drive, if your organization requires it, or if you have space concerns.</span></span> <span data-ttu-id="836e0-110">설정 대화 상자에서 Lync Server 파일의 설치 위치 경로를 사용 가능한 새 드라이브로 간단히 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="836e0-110">You can just change the installation location path for the Lync Server files in the Setup dialog box to a new, available drive.</span></span> <span data-ttu-id="836e0-111">OCSCore를 포함 하 여이 경로에 설치 파일을 설치 하는 경우에는 Lync Server 2013 파일의 나머지 부분도 함께 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="836e0-111">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will deploy there as well.</span></span>



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a><span data-ttu-id="836e0-112">로컬 구성 저장소를 설치 하려면</span><span class="sxs-lookup"><span data-stu-id="836e0-112">To install the Local Configuration store</span></span>

1.  <span data-ttu-id="836e0-113">\\설치 미디어에서 설치\\amd64\\Setup.exe. exe로 이동한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="836e0-113">From your installation media, browse to \\setup\\amd64\\Setup.exe, and then click **OK**.</span></span>

2.  <span data-ttu-id="836e0-114">Microsoft Visual c + + 2012 재배포 가능 패키지를 설치 하 라는 메시지가 표시 되 면 **예**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="836e0-114">If you’re prompted to install the Microsoft Visual C++ 2012 Redistributable, click **Yes**.</span></span>

3.  <span data-ttu-id="836e0-115">**Lync Server 2013 설치 위치** 페이지에서 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="836e0-115">On the **Lync Server 2013 Installation Location** page, click **OK**.</span></span>

4.  <span data-ttu-id="836e0-116">**최종 사용자 사용권 계약** 페이지에서 사용 약관을 검토 한 다음 **라이선스 계약에 동의**하는 조건을 선택한 다음 **확인** 을 클릭 하 여 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="836e0-116">On the **End User License Agreement** page, review the license terms, you’ll need to select **I accept the terms in the license agreement**, and then click **OK** to be able to continue.</span></span>

5.  <span data-ttu-id="836e0-117">배포 마법사 페이지에서 **Lync Server 시스템 설치 또는 업데이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="836e0-117">On the Deployment Wizard page, click **Install or Update Lync Server System**.</span></span>

6.  <span data-ttu-id="836e0-118">**Lync Server 2013** 페이지에서 **Step1: 로컬 구성 저장소 설치 아래**에서 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="836e0-118">On the **Lync Server 2013** page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

7.  <span data-ttu-id="836e0-119">**로컬 구성 저장소 설치** 페이지에서 **중앙 관리 저장소에서 직접 검색** 옵션이 선택 되어 있는지 확인 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="836e0-119">On the **Install Local Configuration Store** page, make sure that the **Retrieve directly from the Central Management store** option is selected, and then click **Next**.</span></span>

8.  <span data-ttu-id="836e0-120">로컬 서버 구성 설치가 완료 되 면 **마침을**클릭 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="836e0-120">When the local server configuration installation is complete, you should click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

