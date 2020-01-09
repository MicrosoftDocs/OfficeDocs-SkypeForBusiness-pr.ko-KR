---
title: 비즈니스용 Skype 서버에서 SIP 트렁크 구성 설정 테스트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'SIP 트렁크 구성 설정은 중재 서버와 PSTN (공개 통신 네트워크) 게이트웨이, IP-공용 분기 교환 (PBX) 또는 서비스 공급자의 SBC (세션 경계 컨트롤러) 간에 관계와 접근 권한 값을 정의 합니다. '
ms.openlocfilehash: bfb09511c8d074555c0b84d2da141a029f63a01a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992565"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="ce185-103">비즈니스용 Skype 서버에서 SIP 트렁크 구성 설정 테스트</span><span class="sxs-lookup"><span data-stu-id="ce185-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="ce185-104">SIP 트렁크 구성 설정은 중재 서버와 PSTN (공개 통신 네트워크) 게이트웨이, IP-공용 분기 교환 (PBX) 또는 서비스 공급자의 SBC (세션 경계 컨트롤러) 간에 관계와 접근 권한 값을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce185-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="ce185-105">이러한 설정은 다음을 지정 하는 등의 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce185-105">These settings do such things as specify:</span></span>

- <span data-ttu-id="ce185-106">Trunks에서 미디어 바이패스를 사용 해야 하는지 여부</span><span class="sxs-lookup"><span data-stu-id="ce185-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="ce185-107">RTCP (실시간 전송 제어 프로토콜) 패킷이 전송 되는 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="ce185-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="ce185-108">각 트렁크에서 보안 실시간 프로토콜 (SRTP) 암호화가 필요한 지 여부</span><span class="sxs-lookup"><span data-stu-id="ce185-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="ce185-109">비즈니스용 Skype 서버를 설치 하면 SIP 트렁크 구성 설정의 전역 컬렉션이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce185-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="ce185-110">또한 관리자는 사이트 범위 또는 서비스 범위 (PSTN 게이트웨이 서비스에만 해당)에서 사용자 지정 설정 모음을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce185-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="ce185-111">또한 관리자는 [set-cstrunkconfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet을 사용 하 여 트렁크가 사용자에 게 전화를 거는 번호를 게이트웨이에서 처리할 수 있는 번호로 변환할 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce185-111">Administrators can also use the [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="ce185-112">트렁크 구성 설정은 Windows PowerShell 및 테스트 Set-cstrunkconfiguration cmdlet을 사용 하 여 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce185-112">Trunk configuration settings can only be tested by using Windows PowerShell and the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="ce185-113">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce185-113">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="ce185-114">**SIP 트렁크 구성 설정을 테스트 하려면**</span><span class="sxs-lookup"><span data-stu-id="ce185-114">**To test SIP trunk configuration settings**</span></span>

<span data-ttu-id="ce185-115">이 명령은 Redmond 사이트의 트렁크 구성 설정이 전화 거는 번호 4255551212를 올바르게 변환할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce185-115">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
