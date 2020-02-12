---
title: 비즈니스용 Skype 서버에서 트렁크 구성 정보 보기
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
description: SIP 트렁크 구성 설정은 중재 서버와 PSTN (공개 통신 네트워크) 게이트웨이, IP-공용 분기 교환 (PBX) 또는 서비스 공급자의 SBC (세션 경계 컨트롤러) 간에 관계와 접근 권한 값을 정의 합니다.
ms.openlocfilehash: 40820729727ec02e5494e69c773d7fbd3d7b1154
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888487"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="a8218-103">비즈니스용 Skype 서버에서 트렁크 구성 정보 보기</span><span class="sxs-lookup"><span data-stu-id="a8218-103">View trunk configuration information in Skype for Business Server</span></span>

<span data-ttu-id="a8218-104">SIP 트렁크 구성 설정은 중재 서버와 PSTN (공개 통신 네트워크) 게이트웨이, IP-공용 분기 교환 (PBX) 또는 서비스 공급자의 SBC (세션 경계 컨트롤러) 간에 관계와 접근 권한 값을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8218-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span>

- <span data-ttu-id="a8218-105">Trunks에서 미디어 바이패스를 사용 해야 하는지 여부</span><span class="sxs-lookup"><span data-stu-id="a8218-105">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="a8218-106">RTCP (실시간 전송 제어 프로토콜) 패킷이 전송 되는 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="a8218-106">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="a8218-107">각 트렁크에서 보안 실시간 프로토콜 (SRTP) 암호화가 필요한 지 여부</span><span class="sxs-lookup"><span data-stu-id="a8218-107">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="a8218-108">비즈니스용 Skype 서버를 설치 하면 SIP 트렁크 구성 설정의 전역 컬렉션이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8218-108">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="a8218-109">또한 관리자는 사이트 범위 또는 서비스 범위 (PSTN 게이트웨이 서비스에만 해당)에서 사용자 지정 설정 모음을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8218-109">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="a8218-110">**비즈니스용 Skype Server 제어판을 사용 하 여 SIP 트렁크 구성 정보를 보려면**</span><span class="sxs-lookup"><span data-stu-id="a8218-110">**To view SIP trunk configuration information by using Skype for Business Server Control Panel**</span></span>

1. <span data-ttu-id="a8218-111">비즈니스용 Skype Server 제어판에서 **음성 라우팅을**클릭 한 다음 **트렁크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8218-111">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="a8218-112">**트렁크 구성** 탭에 모든 트렁크 구성 설정 모음 목록이 표시 됩니다. 각 컬렉션에 대해 **이름**, **범위**, **상태**및 **미디어 바이패스** 속성에 대 한 값을 **PSTN**사용 수, **호출 번호 규칙**, 컬렉션과 연결 된 **번호 규칙** 등으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8218-112">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collections; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="a8218-113">트렁크 구성 설정 모음에 대 한 추가 세부 정보를 보려면 원하는 모음을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8218-113">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="a8218-114">한 번에 한 개의 트렁크 구성 설정 모음에 대 한 자세한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8218-114">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a8218-115">Windows PowerShell cmdlet을 사용 하 여 SIP 트렁크 구성 정보 보기</span><span class="sxs-lookup"><span data-stu-id="a8218-115">Viewing SIP trunk configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="a8218-116">비즈니스용 Skype Server PowerShell 및 Set-cstrunkconfiguration cmdlet을 사용 하 여 SIP 트렁크 구성 설정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8218-116">SIP trunk configuration settings can be viewed by using Skype for Business Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="a8218-117">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 원격 세션 Windows PowerShell에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8218-117">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="a8218-118">원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 https://go.microsoft.com/fwlink/p/?linkId=255876사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a8218-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at https://go.microsoft.com/fwlink/p/?linkId=255876.</span></span> <span data-ttu-id="a8218-119">이 링크를 바꾸거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8218-119">REPLACE OR REMOVE THIS LINK.</span></span>


<span data-ttu-id="a8218-120">**SIP 트렁크 구성 정보를 보려면**</span><span class="sxs-lookup"><span data-stu-id="a8218-120">**To view SIP trunk configuration information**</span></span>

<span data-ttu-id="a8218-121">모든 SIP 트렁크 구성 설정에 대 한 정보를 보려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="a8218-121">To view information about all your SIP trunk configuration settings, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

```powershell
Get-CsTrunkConfiguration
```

<span data-ttu-id="a8218-122">이는 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8218-122">That will return information similar to this:</span></span>

```console
Identity                                  : Global
OutboundTranslationRulesList              : {}
SipResponseCodeTranslationRulesList       : {}
OutboundCallingNumberTranslationRulesList : {}
PstnUsages                                : {}
Description                               :
ConcentratedTopology                      : True
EnableBypass                              : False
EnableMobileTrunkSupport                  : False
EnableReferSupport                        : True
EnableSessionTimer                        : False
EnableSignalBoost                         : False
MaxEarlyDialogs                           : 20
RemovePlusFromUri                         : False
RTCPActiveCalls                           : True
RTCPCallsOnHold                           : True
SRTPMode                                  : Required
EnablePIDFLOSupport                       : False
EnableRTPLatching                         : False
EnableOnlineVoice                         : False
ForwardCallHistory                        : False
Enable3pccRefer                           : False
ForwardPAI                                : False
EnableFastFailoverTimer                   : True
```
<span data-ttu-id="a8218-123">자세한 내용은 Get-help cmdlet에 대 한 도움말 항목 [set-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a8218-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>



