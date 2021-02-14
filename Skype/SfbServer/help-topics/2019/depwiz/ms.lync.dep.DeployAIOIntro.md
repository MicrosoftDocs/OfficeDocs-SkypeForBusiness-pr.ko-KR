---
title: 단일 Standard Edition Server 준비(소개)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
ROBOTS: NOINDEX, NOFOLLOW
description: 중앙 관리 저장소 및 선택한 다른 함께 사용 서비스를 보관할 비즈니스용 Skype 서버 Standard Edition 서버의 설치를 시작하려면 Standard Edition 서버가 될 서버에서 로컬 Administrators 그룹의 구성원으로 로그인해야 합니다. 단일 Standard Edition Server 준비 페이지에 처음 설치에 대한 요구 사항이 자세히 나와 있습니다. 컴퓨터는 서버를 배포할 도메인의 구성원이어야 하며 사용자는 포리스트에 대한 스키마, 포리스트 및 도메인 준비를 성공적으로 완료해야 합니다.
ms.openlocfilehash: 08ea84c0d136339e782c32785c1c4fb536f877cd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820628"
---
# <a name="prepare-single-standard-edition-server-intro"></a><span data-ttu-id="54233-105">단일 Standard Edition Server 준비(소개)</span><span class="sxs-lookup"><span data-stu-id="54233-105">Prepare Single Standard Edition Server (Intro)</span></span>
 
<span data-ttu-id="54233-106">중앙 관리 저장소 및 선택한 다른 함께 사용 서비스를 보관할 비즈니스용 Skype 서버 Standard Edition 서버의 설치를 시작하려면 Standard Edition 서버가 될 서버에서 로컬 Administrators 그룹의 구성원으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54233-106">To begin the installation of a Skype for Business Server Standard Edition server that will hold the Central Management store and other collocated services that you select, you must be logged in as a member of the local Administrators group on the server that will become the Standard Edition server.</span></span> <span data-ttu-id="54233-107">**단일 Standard Edition Server 준비** 페이지에 처음 설치에 대한 요구 사항이 자세히 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54233-107">The **Prepare single Standard Edition Server** page details the requirements for the initial install.</span></span> <span data-ttu-id="54233-108">컴퓨터는 서버를 배포할 도메인의 구성원이어야 하며 사용자는 포리스트에 대한 스키마, 포리스트 및 도메인 준비를 성공적으로 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54233-108">The computer must be a member of the domain in which you are going to deploy it, and you must have successfully completed the Schema, Forest, and Domain prep for your forest.</span></span>
  
<span data-ttu-id="54233-109">이 특정 작업은 Standard Edition 서버를 인프라의 첫 번째 서버로 설치하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="54233-109">This particular task is designed to set up a Standard Edition server as the first server in your infrastructure.</span></span> <span data-ttu-id="54233-110">이 작업에서는 Express인 SQL Server 관리 저장소를 Standard Edition 서버에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="54233-110">This task installs the Central Management store, which is SQL Server Express, onto the Standard Edition server.</span></span> <span data-ttu-id="54233-111">이미 다른 Standard Edition 서버 또는 프런트 엔드 풀을 배포한 경우 **취소** 를 클릭해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54233-111">If you already have another Standard Edition server or Front End pool deployed, you should click **Cancel**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="54233-112">이 작업을 완료한 후 토폴로지 작성기(아직 설치하지 않은 경우)를 설치하고 토폴로지 문서를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="54233-112">After completing this task, you will install Topology Builder (if you have not already installed it) and configure your topology document.</span></span> <span data-ttu-id="54233-113">이 항목에서 설명하는 작업을 완료하여 배포하는 중앙 관리 저장소가 사용 가능해질 때까지 토폴로지 문서를 게시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54233-113">You cannot publish your topology document until you have a Central Management store available—which is deployed by completing the task described in this topic.</span></span> 
  

