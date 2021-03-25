---
title: 네트워크 인터페이스 정보 보기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 이 cmdlet 및 cmdlet을 사용하여 네트워크 인터페이스 Windows PowerShell Get-CsNetworkInterface 있습니다. 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.
ms.openlocfilehash: 0e72b2550413004038b110292b693dda25affaf8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122422"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="53aaf-104">비즈니스용 Skype 서버에서 네트워크 인터페이스 정보 보기</span><span class="sxs-lookup"><span data-stu-id="53aaf-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="53aaf-105">네트워크 인터페이스 정보와 **Get-CsNetworkInterface** cmdlet을 Windows PowerShell 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53aaf-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="53aaf-106">비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53aaf-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="53aaf-107">네트워크 인터페이스 정보를 표시</span><span class="sxs-lookup"><span data-stu-id="53aaf-107">To view network interface information</span></span>

  - <span data-ttu-id="53aaf-108">네트워크 인터페이스 정보를 보시다시피 비즈니스용 Skype 서버 관리 셸에 다음 명령을 입력한 다음 Enter를 눌러야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aaf-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="53aaf-109">이 명령은 각 네트워크 인터페이스에 대해 다음과 비슷한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="53aaf-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="53aaf-110">자세한 내용은 [Get-CsNetworkInterface를 참조합니다.](/powershell/module/skype/Get-CsNetworkInterface)</span><span class="sxs-lookup"><span data-stu-id="53aaf-110">For details, see [Get-CsNetworkInterface](/powershell/module/skype/Get-CsNetworkInterface).</span></span>