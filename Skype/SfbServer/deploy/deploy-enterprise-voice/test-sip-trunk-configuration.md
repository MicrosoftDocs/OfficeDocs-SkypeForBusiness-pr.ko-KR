---
title: 비즈니스용 Skype 서버에서 SIP 트렁크 구성 설정 테스트
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
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: '요약: 비즈니스용 Skype 서버 관리 셸을 사용하여 SIP 트렁크 구성 설정을 테스트하는 방법을 확인합니다.'
ms.openlocfilehash: 8b3a98d54fd0d2dc8bb69e553e0c0a3a7b98b1ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830638"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="7bffd-103">비즈니스용 Skype 서버에서 SIP 트렁크 구성 설정 테스트</span><span class="sxs-lookup"><span data-stu-id="7bffd-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="7bffd-104">**요약:** 비즈니스용 Skype 서버 관리 셸을 사용하여 SIP 트렁크 구성 설정을 테스트하는 방법을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7bffd-104">**Summary:** Learn how to test SIP trunk configuration settings by using the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="7bffd-105">SIP 트렁크 구성 설정은 중재 서버와 PSTN(Public Switched Telephone Network) 게이트웨이, 서비스 공급자의 IP-Public Branch eXchange(PBX) 또는 SBC(Session Border Controller) 간의 관계와 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7bffd-105">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="7bffd-106">이러한 설정은 지정할 경우 다음과 같은 기능을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7bffd-106">These settings do such things as specify:</span></span>
  
- <span data-ttu-id="7bffd-107">트렁크에 미디어 우회를 설정할지 여부</span><span class="sxs-lookup"><span data-stu-id="7bffd-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="7bffd-108">RTCP(Realtime Transport Control Protocol) 패킷이 전송되는 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="7bffd-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="7bffd-109">각 트렁크에 SRTP(Secure Realtime Transport Protocol) 암호화가 필요한지 여부</span><span class="sxs-lookup"><span data-stu-id="7bffd-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="7bffd-110">비즈니스용 Skype 서버를 설치하면 전역 SIP 트렁크 구성 설정 컬렉션이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="7bffd-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="7bffd-111">관리자는 사이트 범위 또는 서비스 범위(PSTN 게이트웨이 서비스만 해당)에서 사용자 지정 설정 컬렉션을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bffd-111">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="7bffd-112">관리자는 또한 Test-CsTrunkConfiguration cmdlet을 사용하여 사용자가 거는 번호를 게이트웨이에서 처리할 수 있는 번호로 트렁크가 변환할 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bffd-112">Administrators can also use the Test-CsTrunkConfiguration cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>
  
<span data-ttu-id="7bffd-113">트렁크 구성 설정은 Windows PowerShell과 [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet을 사용해서만 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bffd-113">Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="7bffd-114">이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bffd-114">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-test-sip-trunk-configuration-settings"></a><span data-ttu-id="7bffd-115">SIP 트렁크 구성 설정을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="7bffd-115">To test SIP trunk configuration settings</span></span>

- <span data-ttu-id="7bffd-116">다음 명령을 실행하면 레드몬드 사이트의 트렁크 구성 설정이 전화 번호(4255551212)를 올바로 변환할 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bffd-116">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


