---
title: 'Lync Server 2013: XMPP 페더레이션 파트너의 협상 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02d72870e4060be6aa4ec428159af7ab19cb68b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="6ae44-102">Lync Server 2013의 XMPP 페더레이션 파트너의 협상 설정</span><span class="sxs-lookup"><span data-stu-id="6ae44-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ae44-103">_**마지막으로 수정한 주제:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="6ae44-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="6ae44-104">XMPP 파트너 구성의 협상 형식에 대 한 설정에는 다양 한 조합이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="6ae44-105">이러한 조합이 모두 유효 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="6ae44-106">이 항목에서 설명 하는 표에서는 유효 하 고 유효 하지 않은 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="6ae44-107">일반적인 구성은 첫 번째 표에 나와 있으며, 두 번째 표에서는 모든 가능 조합을 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="6ae44-108">TLS ( *전송 계층 보안* )도 사용할 수 없는 **경우** 에는 SASL ( *단순 인증 및 보안 계층* )을 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="6ae44-109">SASL은 부호화 되지 않은 (읽을 수 있는) 형식으로 전송 되며, TLS와 같이 다른 방법으로 보호 되지 않는 한 전송 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="6ae44-110">일반적인 XMPP Federation Negotiation 메서드</span><span class="sxs-lookup"><span data-stu-id="6ae44-110">Common XMPP Federation Negotiation Methods</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ae44-111">TLS (전송 계층 보안)</span><span class="sxs-lookup"><span data-stu-id="6ae44-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="6ae44-112">SASL (단순 인증 및 보안 레이어)</span><span class="sxs-lookup"><span data-stu-id="6ae44-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="6ae44-113">Dialback 인증</span><span class="sxs-lookup"><span data-stu-id="6ae44-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="6ae44-114">(으)로 인증 방법이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="6ae44-115">상속자</span><span class="sxs-lookup"><span data-stu-id="6ae44-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ae44-116">필수</span><span class="sxs-lookup"><span data-stu-id="6ae44-116">Required</span></span></p></td>
<td><p><span data-ttu-id="6ae44-117">필수</span><span class="sxs-lookup"><span data-stu-id="6ae44-117">Required</span></span></p></td>
<td><p><span data-ttu-id="6ae44-118">해제</span><span class="sxs-lookup"><span data-stu-id="6ae44-118">False</span></span></p></td>
<td><p><span data-ttu-id="6ae44-119">TLS를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="6ae44-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="6ae44-120">TLS 및 SASL은 SASL 메시지 스트림이 안전한 지 확인 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-120">TLS and SASL required helps to ensure that the SASL message stream is secure.</span></span> <span data-ttu-id="6ae44-121">Dialback는 사용할 수 없으며 XMPP 페더레이션 파트너가 TLS를 필수 또는 선택 사항으로 설정 하지 않은 경우 fallback 메서드에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-121">Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ae44-122">필수</span><span class="sxs-lookup"><span data-stu-id="6ae44-122">Required</span></span></p></td>
<td><p><span data-ttu-id="6ae44-123">선택</span><span class="sxs-lookup"><span data-stu-id="6ae44-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="6ae44-124">False</span><span class="sxs-lookup"><span data-stu-id="6ae44-124">True</span></span></p></td>
<td><p><span data-ttu-id="6ae44-125">TLS, TLS Dialback, TCP Dialback를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="6ae44-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="6ae44-126">XMPP 페더레이션 파트너가 SASL을 optional로 설정 했거나 필요한 SASL을 사용 하는 경우 TLS를 요구 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-126">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used.</span></span> <span data-ttu-id="6ae44-127">SASL을 사용할 수 없는 경우 Dialback를 통해 서 TLS를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-127">If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ae44-128">선택</span><span class="sxs-lookup"><span data-stu-id="6ae44-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="6ae44-129">선택</span><span class="sxs-lookup"><span data-stu-id="6ae44-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="6ae44-130">False</span><span class="sxs-lookup"><span data-stu-id="6ae44-130">True</span></span></p></td>
<td><p><span data-ttu-id="6ae44-131">TLS, TLS Dialback, TCP Dialback를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="6ae44-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="6ae44-132">제공 되는 협상 방법에서는 유연성이 매우 높으며 이러한 설정은 XMPP 페더레이션 파트너의 설정에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-132">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings.</span></span> <span data-ttu-id="6ae44-133">파트너에 TLS 옵션이 있거나 필수 이지만 SASL이 지원 되지 않는 경우에는 TLS Dialback를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-133">If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available.</span></span> <span data-ttu-id="6ae44-134">파트너에 TLS 및 SASL이 optional 또는 required로 설정 되어 있는 경우 SASL을 통해 최적의 TLS 선택이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-134">If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ae44-135">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="6ae44-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="6ae44-136">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="6ae44-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="6ae44-137">False</span><span class="sxs-lookup"><span data-stu-id="6ae44-137">True</span></span></p></td>
<td><p><span data-ttu-id="6ae44-138">TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="6ae44-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="6ae44-139">대부분의 경우에는 TCP Dialback이 유일한 해결책이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-139">In many cases, TCP Dialback is the only possible solution.</span></span> <span data-ttu-id="6ae44-140">다른 옵션 보다는 덜 바람직한 신뢰 수준을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-140">Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="6ae44-141">XMPP 페더레이션 협상 방법 분류표-완료</span><span class="sxs-lookup"><span data-stu-id="6ae44-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ae44-142">TLS (전송 계층 보안)</span><span class="sxs-lookup"><span data-stu-id="6ae44-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="6ae44-143">SASL (단순 인증 및 보안 레이어)</span><span class="sxs-lookup"><span data-stu-id="6ae44-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="6ae44-144">Dialback 인증</span><span class="sxs-lookup"><span data-stu-id="6ae44-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="6ae44-145">필요한 인증 방법</span><span class="sxs-lookup"><span data-stu-id="6ae44-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="6ae44-146">유효 하지 않은 구성에 대 한 노트, 경고 또는 오류</span><span class="sxs-lookup"><span data-stu-id="6ae44-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ae44-147">필수</span><span class="sxs-lookup"><span data-stu-id="6ae44-147">Required</span></span></p></td>
<td><p><span data-ttu-id="6ae44-148">필수</span><span class="sxs-lookup"><span data-stu-id="6ae44-148">Required</span></span></p></td>
<td><p><span data-ttu-id="6ae44-149">False</span><span class="sxs-lookup"><span data-stu-id="6ae44-149">True</span></span></p></td>
<td><p><span data-ttu-id="6ae44-150">TLS를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="6ae44-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="6ae44-151">SASL과 TLS가 모두 필요한 경우 Dialback가 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ae44-152">필수</span><span class="sxs-lookup"><span data-stu-id="6ae44-152">Required</span></span></p></td>
<td><p><span data-ttu-id="6ae44-153">필수</span><span class="sxs-lookup"><span data-stu-id="6ae44-153">Required</span></span></p></td>
<td><p><span data-ttu-id="6ae44-154">해제</span><span class="sxs-lookup"><span data-stu-id="6ae44-154">False</span></span></p></td>
<td><p><span data-ttu-id="6ae44-155">TLS를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="6ae44-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ae44-156">선택</span><span class="sxs-lookup"><span data-stu-id="6ae44-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="6ae44-157">필수</span><span class="sxs-lookup"><span data-stu-id="6ae44-157">Required</span></span></p></td>
<td><p><span data-ttu-id="6ae44-158">False</span><span class="sxs-lookup"><span data-stu-id="6ae44-158">True</span></span></p></td>
<td><p><span data-ttu-id="6ae44-159">TLS, TLS Dialback, TCP Dialback를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="6ae44-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="6ae44-160">SASL에는 TLS가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-160">SASL requires TLS.</span></span> <span data-ttu-id="6ae44-161">TLS를 선택 사항으로 허용 하면 세션 협상이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-161">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ae44-162">선택</span><span class="sxs-lookup"><span data-stu-id="6ae44-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="6ae44-163">필수</span><span class="sxs-lookup"><span data-stu-id="6ae44-163">Required</span></span></p></td>
<td><p><span data-ttu-id="6ae44-164">해제</span><span class="sxs-lookup"><span data-stu-id="6ae44-164">False</span></span></p></td>
<td><p><span data-ttu-id="6ae44-165">TLS를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="6ae44-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="6ae44-166">SASL에는 TLS가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-166">SASL requires TLS.</span></span> <span data-ttu-id="6ae44-167">TLS를 선택 사항으로 허용 하면 세션 협상이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-167">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ae44-168">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="6ae44-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="6ae44-169">필수</span><span class="sxs-lookup"><span data-stu-id="6ae44-169">Required</span></span></p></td>
<td><p><span data-ttu-id="6ae44-170">False</span><span class="sxs-lookup"><span data-stu-id="6ae44-170">True</span></span></p></td>
<td><p><span data-ttu-id="6ae44-171">TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="6ae44-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="6ae44-172">SASL에는 TLS가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-172">SASL requires TLS.</span></span> <span data-ttu-id="6ae44-173">TLS를 선택 사항으로 허용 하면 세션 협상이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-173">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ae44-174">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="6ae44-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="6ae44-175">필수</span><span class="sxs-lookup"><span data-stu-id="6ae44-175">Required</span></span></p></td>
<td><p><span data-ttu-id="6ae44-176">해제</span><span class="sxs-lookup"><span data-stu-id="6ae44-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="6ae44-177">유효 하지 않은 구성</span><span class="sxs-lookup"><span data-stu-id="6ae44-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="6ae44-178">SASL은 TLS를 요구 하 고 TLS를 사용할 수 없기 때문에 SASL/TLS는 성공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-178">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed.</span></span> <span data-ttu-id="6ae44-179">TCP Dialback가 false로 설정 되었으며 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-179">TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ae44-180">필수</span><span class="sxs-lookup"><span data-stu-id="6ae44-180">Required</span></span></p></td>
<td><p><span data-ttu-id="6ae44-181">선택</span><span class="sxs-lookup"><span data-stu-id="6ae44-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="6ae44-182">False</span><span class="sxs-lookup"><span data-stu-id="6ae44-182">True</span></span></p></td>
<td><p><span data-ttu-id="6ae44-183">TLS, tls Dialback를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="6ae44-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ae44-184">필수</span><span class="sxs-lookup"><span data-stu-id="6ae44-184">Required</span></span></p></td>
<td><p><span data-ttu-id="6ae44-185">선택</span><span class="sxs-lookup"><span data-stu-id="6ae44-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="6ae44-186">해제</span><span class="sxs-lookup"><span data-stu-id="6ae44-186">False</span></span></p></td>
<td><p><span data-ttu-id="6ae44-187">TLS를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="6ae44-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ae44-188">선택</span><span class="sxs-lookup"><span data-stu-id="6ae44-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="6ae44-189">선택</span><span class="sxs-lookup"><span data-stu-id="6ae44-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="6ae44-190">False</span><span class="sxs-lookup"><span data-stu-id="6ae44-190">True</span></span></p></td>
<td><p><span data-ttu-id="6ae44-191">TLS, TLS Dialback, TCP Dialback를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="6ae44-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="6ae44-192">SASL에는 TLS가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-192">SASL requires TLS.</span></span> <span data-ttu-id="6ae44-193">TLS를 선택 사항으로 허용 하면 세션 협상이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-193">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ae44-194">선택</span><span class="sxs-lookup"><span data-stu-id="6ae44-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="6ae44-195">선택</span><span class="sxs-lookup"><span data-stu-id="6ae44-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="6ae44-196">해제</span><span class="sxs-lookup"><span data-stu-id="6ae44-196">False</span></span></p></td>
<td><p><span data-ttu-id="6ae44-197">TLS를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="6ae44-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="6ae44-198">SASL에는 TLS가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-198">SASL requires TLS.</span></span> <span data-ttu-id="6ae44-199">TLS를 선택 사항으로 허용 하면 세션 협상이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-199">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ae44-200">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="6ae44-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="6ae44-201">선택</span><span class="sxs-lookup"><span data-stu-id="6ae44-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="6ae44-202">False</span><span class="sxs-lookup"><span data-stu-id="6ae44-202">True</span></span></p></td>
<td><p><span data-ttu-id="6ae44-203">TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="6ae44-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="6ae44-204">SASL에는 TLS가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-204">SASL requires TLS.</span></span> <span data-ttu-id="6ae44-205">TLS를 선택 사항으로 허용 하면 세션 협상이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-205">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ae44-206">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="6ae44-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="6ae44-207">선택</span><span class="sxs-lookup"><span data-stu-id="6ae44-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="6ae44-208">해제</span><span class="sxs-lookup"><span data-stu-id="6ae44-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="6ae44-209">유효 하지 않은 구성</span><span class="sxs-lookup"><span data-stu-id="6ae44-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="6ae44-210">SASL에는 TLS가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-210">SASL requires TLS.</span></span> <span data-ttu-id="6ae44-211">TLS를 선택 사항으로 허용 하면 세션 협상이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-211">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ae44-212">필수</span><span class="sxs-lookup"><span data-stu-id="6ae44-212">Required</span></span></p></td>
<td><p><span data-ttu-id="6ae44-213">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="6ae44-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="6ae44-214">False</span><span class="sxs-lookup"><span data-stu-id="6ae44-214">True</span></span></p></td>
<td><p><span data-ttu-id="6ae44-215">TLS Dialback</span><span class="sxs-lookup"><span data-stu-id="6ae44-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="6ae44-216">구성은 TLS Dialback을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ae44-217">필수</span><span class="sxs-lookup"><span data-stu-id="6ae44-217">Required</span></span></p></td>
<td><p><span data-ttu-id="6ae44-218">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="6ae44-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="6ae44-219">해제</span><span class="sxs-lookup"><span data-stu-id="6ae44-219">False</span></span></p></td>
<td><p><span data-ttu-id="6ae44-220">유효 하지 않은 구성</span><span class="sxs-lookup"><span data-stu-id="6ae44-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="6ae44-221">SASL 또는 Dialback을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ae44-222">선택</span><span class="sxs-lookup"><span data-stu-id="6ae44-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="6ae44-223">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="6ae44-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="6ae44-224">False</span><span class="sxs-lookup"><span data-stu-id="6ae44-224">True</span></span></p></td>
<td><p><span data-ttu-id="6ae44-225">TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="6ae44-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="6ae44-226">다른 끝점의 협상 선택에 따라 TCP 또는 TLS Dialback 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ae44-227">선택</span><span class="sxs-lookup"><span data-stu-id="6ae44-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="6ae44-228">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="6ae44-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="6ae44-229">해제</span><span class="sxs-lookup"><span data-stu-id="6ae44-229">False</span></span></p></td>
<td><p><span data-ttu-id="6ae44-230">유효 하지 않은 구성</span><span class="sxs-lookup"><span data-stu-id="6ae44-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="6ae44-231">SASL 또는 Dialback을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ae44-232">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="6ae44-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="6ae44-233">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="6ae44-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="6ae44-234">False</span><span class="sxs-lookup"><span data-stu-id="6ae44-234">True</span></span></p></td>
<td><p><span data-ttu-id="6ae44-235">TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="6ae44-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="6ae44-236">TCP Dialback만 사용할 수 있는 유일한 협상 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ae44-237">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="6ae44-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="6ae44-238">지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="6ae44-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="6ae44-239">해제</span><span class="sxs-lookup"><span data-stu-id="6ae44-239">False</span></span></p></td>
<td><p><span data-ttu-id="6ae44-240">유효 하지 않은 구성</span><span class="sxs-lookup"><span data-stu-id="6ae44-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="6ae44-241">SASL 또는 Dialback을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae44-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

