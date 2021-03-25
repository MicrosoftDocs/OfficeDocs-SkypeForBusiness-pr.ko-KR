---
title: 프런트 엔드 파일 저장소 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
ROBOTS: NOINDEX, NOFOLLOW
description: Standard Edition 서버 또는 Enterprise Edition 프런트 엔드 풀에 대한 파일 저장소로 사용할 파일 공유를 지정해야 합니다. 기존 파일 공유를 파일 저장소로 사용하거나 파일 공유가 위치할 파일 서버의 FQDN(정규화된 도메인 이름) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다.
ms.openlocfilehash: e1dc0c94880bd161fae41be811847e1b0da3dbb5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118697"
---
# <a name="add-front-end-file-store"></a><span data-ttu-id="a141e-104">프런트 엔드 파일 저장소 추가</span><span class="sxs-lookup"><span data-stu-id="a141e-104">Add Front End File Store</span></span>

<span data-ttu-id="a141e-p102">Standard Edition 서버 또는 Enterprise Edition 프런트 엔드 풀에 대한 파일 저장소로 사용할 파일 공유를 지정해야 합니다. 기존 파일 공유를 파일 저장소로 사용하거나 파일 공유가 위치할 파일 서버의 FQDN(정규화된 도메인 이름) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a141e-p102">You must specify a file share to be used as the file store for the Standard Edition server or Enterprise Edition Front End pool. You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a141e-107">파일 공유는 Enterprise Edition 프런트 엔드 서버에는 위치할 수 없지만 Standard Edition 서버에는 위치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a141e-107">The file share cannot be located on the Enterprise Edition Front End Server, but can be located on a Standard Edition server.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a141e-108">파일 공유를 만들기 전에 토폴로지 작성기에서 파일 공유를 정의할 수 있지만 토폴로지를 게시하기 전에 정의한, 정의된 위치에 파일 공유를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a141e-108">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location you define before you publish the topology.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a141e-109">토폴로지에 엔터프라이즈 프런트 엔드 풀 또는 Standard Edition 서버를 추가할 때 토폴로지 작성기에서 파일 저장소를 설정하고 파일 저장소에 사용할 파일 공유에 대한 DACL(사용자별 액세스 제어 목록)을 구성할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a141e-109">When you add an Enterprise Front End pool or Standard Edition server to your topology, Topology Builder must be able to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="a141e-110">이렇게 하려면 토폴로지 작성기를 실행하여 새 토폴로지를 게시할 때 파일 공유에 대한 모든 권한(읽기/쓰기/수정)을 가진 계정으로 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a141e-110">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="a141e-111">파일 공유의 저장소 지원에 대한 자세한 내용은 지원 가능성 설명서의 File [Storage Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) 및 배포 [설명서의 SQL Server Data and Log File Placement를](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a141e-111">For details about storage support for file shares, see [File Storage Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) in the Supportability documentation and [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in the Deployment documentation.</span></span> <span data-ttu-id="a141e-112">파일 공유 배치에 대한 자세한 내용은 지원 가능성 설명서의 [지원되는 서버 배치](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a141e-112">For details about collocation of the file share, see [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) in the Supportability documentation.</span></span> <span data-ttu-id="a141e-113">Enterprise Edition 프런트 엔드 풀에 대한 토폴로지를 설계하는 방법에 대한 자세한 내용은 배포 설명서의 [프런트 엔드 풀 정의 및 구성](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a141e-113">For details about designing the topology for an Enterprise Edition Front End pool, see [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) in the Deployment documentation.</span></span>