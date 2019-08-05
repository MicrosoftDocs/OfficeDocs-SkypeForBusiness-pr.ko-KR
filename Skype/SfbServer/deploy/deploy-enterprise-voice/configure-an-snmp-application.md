---
title: 비즈니스용 Skype 서버에서 SNMP 응용 프로그램 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: 비즈니스용 Skype Server Enterprise Voice의 E9-1-1에서 작동 하도록 SNMP 응용 프로그램을 구성 합니다.
ms.openlocfilehash: 575c982dae20ed085e49690edfbb141786390516
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197436"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a><span data-ttu-id="77223-103">비즈니스용 Skype 서버에서 SNMP 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="77223-103">Configure an SNMP application in Skype for Business Server</span></span>
 
<span data-ttu-id="77223-104">비즈니스용 Skype Server Enterprise Voice의 E9-1-1에서 작동 하도록 SNMP 응용 프로그램을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="77223-104">Configure an SNMP application to work with E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="77223-105">비즈니스용 Skype 서버에는 위치 정보 서비스를 포트 및 스위치 정보를 사용 하 여 MAC 주소와 일치 하는 SNMP (단순 네트워크 관리 프로토콜) 응용 프로그램에 연결 하는 데 사용할 수 있는 표준 웹 서비스 인터페이스가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77223-105">Skype for Business Server includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span> 
  
<span data-ttu-id="77223-106">SNMP 응용 프로그램이 설치 되어 있고 위치 정보 서비스가 위치 데이터베이스에서 일치 하는 항목을 찾지 못하는 경우 위치 정보 서비스는 클라이언트에서 제공 하는 MAC 주소를 사용 하 여 응용 프로그램을 자동으로 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="77223-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="77223-107">위치 정보 서비스는 SNMP 응용 프로그램에서 반환 된 포트 및 스위치 정보를 사용 하 여 위치 데이터베이스를 다시 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="77223-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="77223-108">MAC 주소는 Windows 8을 실행 하는 컴퓨터에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77223-108">MAC addresses are not available on computers running Windows 8.</span></span> 
  
### <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="77223-109">SNMP 응용 프로그램 URL을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="77223-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="77223-110">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="77223-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="77223-111">SNMP 응용 프로그램의 URL을 구성 하려면 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="77223-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="77223-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="77223-112">See also</span></span>

[<span data-ttu-id="77223-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="77223-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

