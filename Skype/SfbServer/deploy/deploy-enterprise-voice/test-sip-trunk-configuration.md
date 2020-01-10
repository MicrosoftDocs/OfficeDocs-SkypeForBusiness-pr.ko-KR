---
title: 비즈니스용 Skype 서버에서 SIP 트렁크 구성 설정 테스트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: '요약: 비즈니스용 Skype 서버 관리 셸을 사용 하 여 SIP 트렁크 구성 설정을 테스트 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 7f0d4f4046a5bffbde4267b5de8ae651a35a2add
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001978"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="6d4f8-103">비즈니스용 Skype 서버에서 SIP 트렁크 구성 설정 테스트</span><span class="sxs-lookup"><span data-stu-id="6d4f8-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="6d4f8-104">**요약:** 비즈니스용 Skype 서버 관리 셸을 사용 하 여 SIP 트렁크 구성 설정을 테스트 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="6d4f8-104">**Summary:** Learn how to test SIP trunk configuration settings by using the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="6d4f8-105">SIP 트렁크 구성 설정은 중재 서버와 PSTN (공개 통신 네트워크) 게이트웨이, IP-공용 분기 교환 (PBX) 또는 서비스 공급자의 SBC (세션 경계 컨트롤러) 간에 관계와 접근 권한 값을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d4f8-105">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="6d4f8-106">이러한 설정은 다음을 지정 하는 등의 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d4f8-106">These settings do such things as specify:</span></span>
  
- <span data-ttu-id="6d4f8-107">Trunks에서 미디어 바이패스를 사용 해야 하는지 여부</span><span class="sxs-lookup"><span data-stu-id="6d4f8-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="6d4f8-108">RTCP (실시간 전송 제어 프로토콜) 패킷이 전송 되는 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="6d4f8-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="6d4f8-109">각 트렁크에서 보안 실시간 전송 프로토콜 (SRTP) 암호화가 필요한 지 여부</span><span class="sxs-lookup"><span data-stu-id="6d4f8-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="6d4f8-110">비즈니스용 Skype 서버를 설치 하면 SIP 트렁크 구성 설정의 전역 컬렉션이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d4f8-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="6d4f8-111">또한 관리자는 사이트 범위 또는 서비스 범위 (PSTN 게이트웨이 서비스에만 해당)에서 사용자 지정 설정 모음을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4f8-111">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="6d4f8-112">또한 관리자는 Set-cstrunkconfiguration cmdlet을 사용 하 여 트렁크가 사용자에 게 전화를 거는 번호를 게이트웨이에서 처리할 수 있는 번호로 변환할 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4f8-112">Administrators can also use the Test-CsTrunkConfiguration cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>
  
<span data-ttu-id="6d4f8-113">트렁크 구성 설정은 Windows PowerShell 및 [테스트 set-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet을 사용 하 여 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4f8-113">Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="6d4f8-114">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 비즈니스용 Skype Server Management Shell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4f8-114">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-test-sip-trunk-configuration-settings"></a><span data-ttu-id="6d4f8-115">SIP 트렁크 구성 설정을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="6d4f8-115">To test SIP trunk configuration settings</span></span>

- <span data-ttu-id="6d4f8-116">이 명령은 Redmond 사이트의 트렁크 구성 설정이 전화 거는 번호 4255551212를 올바르게 변환할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d4f8-116">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


