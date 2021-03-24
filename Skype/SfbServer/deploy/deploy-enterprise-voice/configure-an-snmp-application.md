---
title: 비즈니스용 Skype 서버에서 SNMP 응용 프로그램 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: 비즈니스용 Skype 서버 서버에서 E9-1-1과 함께 작동하도록 SNMP 응용 프로그램을 Enterprise Voice.
ms.openlocfilehash: f8b4c7503524dacdc20e85fc68f0a79286e38c2e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103634"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a><span data-ttu-id="936c2-103">비즈니스용 Skype 서버에서 SNMP 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="936c2-103">Configure an SNMP application in Skype for Business Server</span></span>
 
<span data-ttu-id="936c2-104">비즈니스용 Skype 서버 서버에서 E9-1-1과 함께 작동하도록 SNMP 응용 프로그램을 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="936c2-104">Configure an SNMP application to work with E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="936c2-105">비즈니스용 Skype 서버에는 위치 정보 서비스를 포트 및 스위치 정보와 MAC 주소와 일치하는 SNMP(Simple Network Management Protocol) 응용 프로그램에 연결하는 데 사용할 수 있는 표준 웹 서비스 인터페이스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="936c2-105">Skype for Business Server includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span> 
  
<span data-ttu-id="936c2-106">SNMP 응용 프로그램이 설치되고 위치 정보 서비스에서 위치 데이터베이스에서 일치를 찾지 못하는 경우 위치 정보 서비스는 클라이언트에서 제공하는 MAC 주소를 사용하여 응용 프로그램을 자동으로 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="936c2-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="936c2-107">그런 다음 위치 정보 서비스는 SNMP 응용 프로그램에서 반환된 포트 및 스위치 정보를 사용하여 위치 데이터베이스를 다시 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="936c2-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="936c2-108">MAC 주소는 Windows 8을 실행하는 컴퓨터에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="936c2-108">MAC addresses are not available on computers running Windows 8.</span></span> 
  
### <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="936c2-109">SNMP 응용 프로그램 URL을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="936c2-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="936c2-110">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="936c2-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="936c2-111">다음 cmdlet를 실행하여 SNMP 응용 프로그램에 대한 URL을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="936c2-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span> 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="936c2-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="936c2-112">See also</span></span>

[<span data-ttu-id="936c2-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="936c2-113">Set-CsWebServiceConfiguration</span></span>](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)