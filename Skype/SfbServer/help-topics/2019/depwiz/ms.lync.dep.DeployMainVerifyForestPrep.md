---
title: 포리스트 준비 복제 확인
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
ROBOTS: NOINDEX, NOFOLLOW
description: 포리스트 준비 중 개체 만들기 및 전역 카탈로그 복제가 정상적으로 수행되었는지 확인하려면 다음을 수행합니다.
ms.openlocfilehash: 299b738bbfa14ad13825e5c08e87c03167c9f4cc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801598"
---
# <a name="verify-replication-of-forest-preparation"></a><span data-ttu-id="94341-103">포리스트 준비 복제 확인</span><span class="sxs-lookup"><span data-stu-id="94341-103">Verify Replication of Forest Preparation</span></span>
 
<span data-ttu-id="94341-104">포리스트 준비 중 개체 만들기 및 전역 카탈로그 복제가 정상적으로 수행되었는지 확인하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="94341-104">To confirm that the replication of the Global Catalog and the creation of objects during Forest Preparation have been successful, do the following:</span></span>
  
1. <span data-ttu-id="94341-105">포리스트 준비가 실행된 포리스트의 도메인 컨트롤러(가급적이면 다른 도메인 컨트롤러의 원격 사이트)에서 **Active Directory 사용자 및 컴퓨터** 를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="94341-105">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
2. <span data-ttu-id="94341-106">**Active Directory 사용자 및 컴퓨터** 에서 포리스트 또는 자식 도메인의 도메인 이름을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="94341-106">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
3. <span data-ttu-id="94341-107">왼쪽 창에서 **Users** 컨테이너를 클릭하고 오른쪽 창에서 유니버설 그룹 CsAdministrator를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="94341-107">Click the **Users** container on the left side pane and look for the Universal group CsAdministrator in the right side pane.</span></span> <span data-ttu-id="94341-108">Cs로 시작하는 다른 여덟 가지 새 유니버설 그룹 중 CsAdministrator가 있는 경우 포리스트 준비 복제가 성공한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="94341-108">If CsAdministrator (among eight other new Universal groups that begin with Cs) is present, replication of the Forest Preparation has been successful.</span></span>
    
4. <span data-ttu-id="94341-p102">그룹이 아직 없으면 복제를 적용하거나 15분간 기다린 후 오른쪽 창을 새로 고칠 수 있습니다. 그룹이 나타나면 복제가 완료된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="94341-p102">If the group(s) is not yet present, you can force the replication or wait 15 minutes and refresh the right side pane. When the groups are present, replication is complete.</span></span>
    
> [!TIP]
> <span data-ttu-id="94341-111">비즈니스용 Skype 서버 배포 마법사에서 만든 로그 파일을 검토하려면 배포 마법사를 실행한 컴퓨터의 해당 단계를 실행한 Active Directory 도메인 서비스 사용자의 Users 디렉터리에서 로그 파일을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94341-111">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="94341-112">예를 들어 사용자가 도메인 Contoso.net 도메인 관리자로 로그인한 경우 로그 파일은 C:\Users\Administrator.Contoso\AppData\Local\Temp에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94341-112">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

