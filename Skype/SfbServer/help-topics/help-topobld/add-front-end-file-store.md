---
title: 프런트 엔드 파일 저장소 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
description: Standard Edition 서버 또는 Enterprise Edition 프런트 엔드 풀에 대한 파일 저장소로 사용할 파일 공유를 지정해야 합니다. 기존 파일 공유를 파일 저장소로 사용하거나 파일 공유가 위치할 파일 서버의 FQDN(정규화된 도메인 이름) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다.
ms.openlocfilehash: 66289799ba69fee037d2dbe465be78cf7d77be67
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824118"
---
# <a name="add-front-end-file-store"></a><span data-ttu-id="ea0f5-104">프런트 엔드 파일 저장소 추가</span><span class="sxs-lookup"><span data-stu-id="ea0f5-104">Add Front End File Store</span></span>

<span data-ttu-id="ea0f5-p102">Standard Edition 서버 또는 Enterprise Edition 프런트 엔드 풀에 대한 파일 저장소로 사용할 파일 공유를 지정해야 합니다. 기존 파일 공유를 파일 저장소로 사용하거나 파일 공유가 위치할 파일 서버의 FQDN(정규화된 도메인 이름) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea0f5-p102">You must specify a file share to be used as the file store for the Standard Edition server or Enterprise Edition Front End pool. You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ea0f5-107">파일 공유는 Enterprise Edition 프런트 엔드 서버에 있을 수 없지만 Standard Edition 서버에는 위치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea0f5-107">The file share cannot be located on the Enterprise Edition Front End Server, but can be located on a Standard Edition server.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ea0f5-108">파일 공유를 만들기 전에 토폴로지 작성기에서 파일 공유를 정의할 수 있지만 토폴로지를 게시하기 전에 정의한, 정의된 위치에 파일 공유를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0f5-108">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location you define before you publish the topology.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ea0f5-109">토폴로지에 엔터프라이즈 프런트 엔드 풀 또는 Standard Edition 서버를 추가할 때 토폴로지 작성기에서 파일 저장소를 설정하고 파일 저장소에 사용할 파일 공유에 대한 DACL(사용자별 액세스 제어 목록)을 구성할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0f5-109">When you add an Enterprise Front End pool or Standard Edition server to your topology, Topology Builder must be able to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="ea0f5-110">이렇게 하려면 토폴로지 작성기를 실행하여 새 토폴로지를 게시할 때 파일 공유에 대한 모든 권한(읽기/쓰기/수정)을 가진 계정으로 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0f5-110">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="ea0f5-111">파일 공유에 대한 저장소 지원에 [](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) 대한 자세한 내용은 지원 가능성 설명서의 파일 저장소 지원 및 배포 설명서의 SQL Server 데이터 및 로그 [파일](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) 배치를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ea0f5-111">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="ea0f5-112">파일 공유 배치에 대한 자세한 내용은 지원 가능성 설명서의 [지원되는 서버 배치](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ea0f5-112">For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="ea0f5-113">Enterprise Edition 프런트 엔드 풀에 대한 토폴로지를 설계하는 방법에 대한 자세한 내용은 배포 설명서의 [프런트 엔드 풀 정의 및 구성](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ea0f5-113">For details about designing the topology for an Enterprise Edition Front End pool, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>


