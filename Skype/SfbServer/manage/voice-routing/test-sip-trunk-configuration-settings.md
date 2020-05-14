---
title: 비즈니스용 Skype 서버에서 SIP 트렁크 구성 설정 테스트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'SIP 트렁크 구성 설정은 중재 서버 및 PSTN(공중 전화망) 게이트웨이, IP-PBX(Public Branch Exchange) 또는 서비스 공급자의 SBC(세션 경계 컨트롤러) 사이의 관계 및 기능을 정의합니다. '
ms.openlocfilehash: bed342de3f602499f16b9f27ee0726f10d2c867e
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "42048191"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="eb6be-103">비즈니스용 Skype 서버에서 SIP 트렁크 구성 설정 테스트</span><span class="sxs-lookup"><span data-stu-id="eb6be-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="eb6be-p101">SIP 트렁크 구성 설정은 중재 서버 및 PSTN(공중 전화망) 게이트웨이, IP-PBX(Public Branch Exchange) 또는 서비스 공급자의 SBC(세션 경계 컨트롤러) 사이의 관계 및 기능을 정의합니다. 이러한 설정은 지정할 경우 다음과 같은 기능을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb6be-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

- <span data-ttu-id="eb6be-106">트렁크에 미디어 우회를 설정할지 여부</span><span class="sxs-lookup"><span data-stu-id="eb6be-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="eb6be-107">RTCP(Real-time Transport Control Protocol) 패킷이 전송되는 조건</span><span class="sxs-lookup"><span data-stu-id="eb6be-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="eb6be-108">SRTP(Secure Real-time Protocol) 암호화가 각 트렁크에 필요한지 여부</span><span class="sxs-lookup"><span data-stu-id="eb6be-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="eb6be-109">비즈니스용 Skype 서버를 설치 하면 SIP 트렁크 구성 설정의 전역 모음이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="eb6be-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="eb6be-110">또한 관리자가 사이트 범위 또는 서비스 범위(PSTN 게이트웨이 서비스 전용)에서 사용자 지정 설정 컬렉션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb6be-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="eb6be-111">또한 관리자는 [get-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet을 사용 하 여 트렁크가 사용자에 게 전화를 거는 번호를 게이트웨이에서 처리할 수 있는 번호로 변환할 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb6be-111">Administrators can also use the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="eb6be-112">트렁크 구성 설정은 Windows PowerShell과 Test-CsTrunkConfiguration cmdlet을 사용해서만 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb6be-112">Trunk configuration settings can only be tested by using Windows PowerShell and the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="eb6be-113">이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb6be-113">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="eb6be-114">**SIP 트렁크 구성 설정을 테스트 하려면**</span><span class="sxs-lookup"><span data-stu-id="eb6be-114">**To test SIP trunk configuration settings**</span></span>

<span data-ttu-id="eb6be-115">다음 명령을 실행하면 레드몬드 사이트의 트렁크 구성 설정이 전화 번호(4255551212)를 올바로 변환할 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb6be-115">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
