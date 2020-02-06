---
title: 인증서 요청, 설치 또는 할당
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainCerts
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 332ec40f-78be-440a-8c1d-ada6114897db
ROBOTS: NOINDEX, NOFOLLOW
description: '3단계: 인증서 요청, 설치 또는 할당에서 실행을 클릭하면 인증서 마법사가 시작됩니다. 마법사를 통해 구성 된 인증서는 중앙 관리 저장소에 대 한 토폴로지 작성기에서 구성 하 고 게시 하는 비즈니스용 Skype 서버 토폴로지 정의를 기반으로 합니다. 조직의 온라인 CA(인증 기관)에 대해 인증서 마법사를 성공적으로 실행하려면 컴퓨터 로컬 관리자 그룹의 구성원인 사용자로 컴퓨터에 로그온해야 합니다. 또한 컴퓨터 및 CA가 있는 도메인의 인증된 도메인 사용자여야 합니다. 인증서 마법사는 조직의 CA에 액세스 하기 위한 대체 자격 증명을 지정 하는 기능을 제공 합니다.'
ms.openlocfilehash: b60c81ab2c777cbd8829b5951ac9c931b9382b86
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798355"
---
# <a name="request-install-or-assign-certificates"></a><span data-ttu-id="57668-107">인증서 요청, 설치 또는 할당</span><span class="sxs-lookup"><span data-stu-id="57668-107">Request, Install, or Assign Certificates</span></span>
 
 <span data-ttu-id="57668-108">**3단계: 인증서 요청, 설치 또는 할당**에서 **실행**을 클릭하면 인증서 마법사가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="57668-108">**Step 3: Request, Install or Assign Certificates** starts the Certificate Wizard when you click **Run**.</span></span> <span data-ttu-id="57668-109">마법사를 통해 구성 된 인증서는 중앙 관리 저장소에 대 한 토폴로지 작성기에서 구성 하 고 게시 하는 비즈니스용 Skype 서버 토폴로지 정의를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="57668-109">The certificates that are configured through the wizard are based on the definition of the Skype for Business Server topology that is configured and published by Topology Builder to the Central Management store.</span></span> <span data-ttu-id="57668-110">조직의 온라인 CA(인증 기관)에 대해 인증서 마법사를 성공적으로 실행하려면 컴퓨터 로컬 관리자 그룹의 구성원인 사용자로 컴퓨터에 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57668-110">To successfully run the Certificate Wizard for an online certification authority (CA) in your organization, you must be logged on to the computer as a user who is a member of the computer local administrators group.</span></span> <span data-ttu-id="57668-111">또한 컴퓨터 및 CA가 있는 도메인의 인증된 도메인 사용자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57668-111">You must also be an authenticated Domain User in the domain where the computer and the CA exist.</span></span> <span data-ttu-id="57668-112">인증서 마법사는 조직의 CA에 액세스 하기 위한 대체 자격 증명을 지정 하는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="57668-112">The certificate wizard does provide the ability to specify alternate credentials for access your organization's CA.</span></span>
  
> [!NOTE]
> <span data-ttu-id="57668-p103">또한 인증서 마법사를 사용하여 공용 CA 또는 다른 오프라인 PKI(공개 키 인프라)로 전송된 오프라인 인증서 요청을 요청 및 처리할 수 있습니다. 컴퓨터에 로그온하는 데 필요한 특정 그룹 구성원 자격 외에 오프라인 요청을 생성하는 데 필요한 특정 그룹 구성원 자격은 없습니다. 공용 CA 응답을 처리하고 인증서를 컴퓨터 및 역할에 할당하려면 로컬 관리자 그룹의 구성원이나 이와 동일한 사용자 권한을 가진 계정으로 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57668-p103">You can also use the Certificate Wizard to request and process offline certificate requests that are sent to a public CA or other offline public key infrastructure (PKI). There are no specific group memberships, other than those needed to log on to the computer, to generate an offline request. To process the public CA response and to assign the certificate to the computer and role, you must be logged on as a member of the local Administrators group or equivalent.</span></span> 
  

