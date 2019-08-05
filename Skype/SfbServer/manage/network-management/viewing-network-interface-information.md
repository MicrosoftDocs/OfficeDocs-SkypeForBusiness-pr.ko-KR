---
title: 네트워크 인터페이스 정보 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Windows PowerShell 및 CsNetworkInterface cmdlet을 사용 하 여 네트워크 인터페이스 정보를 볼 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.
ms.openlocfilehash: ac0df8450b938a377e1325f9c3179b4650b31bdf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188526"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="352f2-104">비즈니스용 Skype 서버에서 네트워크 인터페이스 정보 보기</span><span class="sxs-lookup"><span data-stu-id="352f2-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="352f2-105">Windows PowerShell 및 **CsNetworkInterface** cmdlet을 사용 하 여 네트워크 인터페이스 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="352f2-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="352f2-106">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="352f2-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="352f2-107">네트워크 인터페이스 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="352f2-107">To view network interface information</span></span>

  - <span data-ttu-id="352f2-108">네트워크 인터페이스 정보를 보려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="352f2-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="352f2-109">이 명령은 각 네트워크 인터페이스에 대해 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="352f2-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="352f2-110">자세한 내용은 [Get-help CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="352f2-110">For details, see [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span></span>


