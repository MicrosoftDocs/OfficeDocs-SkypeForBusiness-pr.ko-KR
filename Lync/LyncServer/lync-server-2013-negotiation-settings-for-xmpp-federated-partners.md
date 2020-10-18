---
title: 'Lync Server 2013: XMPP 페더레이션 파트너에 대 한 협상 설정'
description: 'Lync Server 2013: XMPP 페더레이션 파트너에 대 한 협상 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ac3d9c69d407dc750a1afb35f0a448869a88f09
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578644"
---
# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="a1d55-103">Lync Server 2013의 XMPP 페더레이션 파트너에 대 한 협상 설정</span><span class="sxs-lookup"><span data-stu-id="a1d55-103">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1d55-104">_**마지막으로 수정 된 항목:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="a1d55-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="a1d55-105">XMPP 파트너 구성의 협상 유형에 대 한 설정은 다양 한 조합으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-105">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="a1d55-106">이러한 모든 조합은 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-106">Not all of these combinations are valid.</span></span> <span data-ttu-id="a1d55-107">이 항목에서 설명 하는 표에서는 유효 하 고 유효 하지 않은 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-107">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="a1d55-108">일반적인 구성에 대 한 자세한 내용은 두 번째 표에 나오는 모든 가능한 조합을 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-108">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="a1d55-109">TLS ( *전송 계층 보안* )도 사용할 수 있는 **경우가 아니면** SASL ( *단순 인증 및 보안 계층* )을 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-109">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="a1d55-110">SASL은 부호화 되지 않은 (읽을 수 있는) 형식으로 전송 되며 TLS와 같은 다른 방법으로 보호 되지 않으면 전송 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-110">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="a1d55-111">일반 XMPP 페더레이션 협상 방법</span><span class="sxs-lookup"><span data-stu-id="a1d55-111">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="a1d55-112">TLS (전송 계층 보안)</span><span class="sxs-lookup"><span data-stu-id="a1d55-112">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="a1d55-113">SASL (Simple Authentication and Security Layer)</span><span class="sxs-lookup"><span data-stu-id="a1d55-113">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="a1d55-114">전화 접속 회의 인증</span><span class="sxs-lookup"><span data-stu-id="a1d55-114">Dialback Authentication</span></span></th>
<th><span data-ttu-id="a1d55-115">예상 인증 방법</span><span class="sxs-lookup"><span data-stu-id="a1d55-115">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="a1d55-116">참고</span><span class="sxs-lookup"><span data-stu-id="a1d55-116">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1d55-117">필수</span><span class="sxs-lookup"><span data-stu-id="a1d55-117">Required</span></span></p></td>
<td><p><span data-ttu-id="a1d55-118">필수</span><span class="sxs-lookup"><span data-stu-id="a1d55-118">Required</span></span></p></td>
<td><p><span data-ttu-id="a1d55-119">False</span><span class="sxs-lookup"><span data-stu-id="a1d55-119">False</span></span></p></td>
<td><p><span data-ttu-id="a1d55-120">EAP-TLS를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="a1d55-120">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="a1d55-121">TLS 및 SASL 필요한 경우 SASL 메시지 스트림이 안전한 지 확인 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-121">TLS and SASL required helps to ensure that the SASL message stream is secure.</span></span> <span data-ttu-id="a1d55-122">XMPP 페더레이션 파트너가 TLS를 필수 또는 선택으로 설정 하지 않은 경우에는 전화 접속 회의을 사용할 수 없으며 대체 방법으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-122">Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1d55-123">필수</span><span class="sxs-lookup"><span data-stu-id="a1d55-123">Required</span></span></p></td>
<td><p><span data-ttu-id="a1d55-124">선택</span><span class="sxs-lookup"><span data-stu-id="a1d55-124">Optional</span></span></p></td>
<td><p><span data-ttu-id="a1d55-125">True</span><span class="sxs-lookup"><span data-stu-id="a1d55-125">True</span></span></p></td>
<td><p><span data-ttu-id="a1d55-126">TLS, TLS 전화 접속 회의, TCP 전화 접속 회의을 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="a1d55-126">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="a1d55-127">XMPP 페더레이션 파트너가 SASL을 optional로 설정 했거나 필요한 SASL을 사용 하는 경우 TLS를 요구 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-127">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used.</span></span> <span data-ttu-id="a1d55-128">SASL을 사용할 수 없는 경우 전화 접속 회의 over TLS가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-128">If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1d55-129">선택</span><span class="sxs-lookup"><span data-stu-id="a1d55-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="a1d55-130">선택</span><span class="sxs-lookup"><span data-stu-id="a1d55-130">Optional</span></span></p></td>
<td><p><span data-ttu-id="a1d55-131">True</span><span class="sxs-lookup"><span data-stu-id="a1d55-131">True</span></span></p></td>
<td><p><span data-ttu-id="a1d55-132">TLS, TLS 전화 접속 회의, TCP 전화 접속 회의을 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="a1d55-132">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="a1d55-133">협상 방법의 유연성이 매우 뛰어납니다, 이러한 설정은 XMPP 페더레이션 파트너의 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-133">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings.</span></span> <span data-ttu-id="a1d55-134">파트너가 TLS 옵션 또는 필수를 포함 하지만 SASL이 지원 되지 않는 경우 TLS 전화 접속 회의를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-134">If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available.</span></span> <span data-ttu-id="a1d55-135">파트너에 TLS 및 SASL이 optional 또는 required로 설정 되어 있으면 SASL을 통해 최적의 TLS 선택이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-135">If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1d55-136">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="a1d55-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a1d55-137">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="a1d55-137">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a1d55-138">True</span><span class="sxs-lookup"><span data-stu-id="a1d55-138">True</span></span></p></td>
<td><p><span data-ttu-id="a1d55-139">TCP 전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="a1d55-139">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="a1d55-140">대부분의 경우 TCP 전화 접속 회의은 유일한 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-140">In many cases, TCP Dialback is the only possible solution.</span></span> <span data-ttu-id="a1d55-141">다른 옵션 보다 덜 바람직한 방법으로는 몇 가지 신뢰 수준이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-141">Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="a1d55-142">XMPP 페더레이션 협상 방법 매트릭스-전체</span><span class="sxs-lookup"><span data-stu-id="a1d55-142">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="a1d55-143">TLS (전송 계층 보안)</span><span class="sxs-lookup"><span data-stu-id="a1d55-143">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="a1d55-144">SASL (Simple Authentication and Security Layer)</span><span class="sxs-lookup"><span data-stu-id="a1d55-144">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="a1d55-145">전화 접속 회의 인증</span><span class="sxs-lookup"><span data-stu-id="a1d55-145">Dialback Authentication</span></span></th>
<th><span data-ttu-id="a1d55-146">예상 인증 방법</span><span class="sxs-lookup"><span data-stu-id="a1d55-146">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="a1d55-147">유효 하지 않은 구성에 대 한 메모, 경고 또는 오류</span><span class="sxs-lookup"><span data-stu-id="a1d55-147">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1d55-148">필수</span><span class="sxs-lookup"><span data-stu-id="a1d55-148">Required</span></span></p></td>
<td><p><span data-ttu-id="a1d55-149">필수</span><span class="sxs-lookup"><span data-stu-id="a1d55-149">Required</span></span></p></td>
<td><p><span data-ttu-id="a1d55-150">True</span><span class="sxs-lookup"><span data-stu-id="a1d55-150">True</span></span></p></td>
<td><p><span data-ttu-id="a1d55-151">EAP-TLS를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="a1d55-151">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a1d55-152">SASL 및 TLS가 필요한 경우에는 전화 접속 회의가 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-152">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1d55-153">필수</span><span class="sxs-lookup"><span data-stu-id="a1d55-153">Required</span></span></p></td>
<td><p><span data-ttu-id="a1d55-154">필수</span><span class="sxs-lookup"><span data-stu-id="a1d55-154">Required</span></span></p></td>
<td><p><span data-ttu-id="a1d55-155">False</span><span class="sxs-lookup"><span data-stu-id="a1d55-155">False</span></span></p></td>
<td><p><span data-ttu-id="a1d55-156">EAP-TLS를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="a1d55-156">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1d55-157">선택</span><span class="sxs-lookup"><span data-stu-id="a1d55-157">Optional</span></span></p></td>
<td><p><span data-ttu-id="a1d55-158">필수</span><span class="sxs-lookup"><span data-stu-id="a1d55-158">Required</span></span></p></td>
<td><p><span data-ttu-id="a1d55-159">True</span><span class="sxs-lookup"><span data-stu-id="a1d55-159">True</span></span></p></td>
<td><p><span data-ttu-id="a1d55-160">TLS, TLS 전화 접속 회의, TCP 전화 접속 회의을 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="a1d55-160">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a1d55-161">SASL에는 TLS가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-161">SASL requires TLS.</span></span> <span data-ttu-id="a1d55-162">TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-162">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1d55-163">선택</span><span class="sxs-lookup"><span data-stu-id="a1d55-163">Optional</span></span></p></td>
<td><p><span data-ttu-id="a1d55-164">필수</span><span class="sxs-lookup"><span data-stu-id="a1d55-164">Required</span></span></p></td>
<td><p><span data-ttu-id="a1d55-165">False</span><span class="sxs-lookup"><span data-stu-id="a1d55-165">False</span></span></p></td>
<td><p><span data-ttu-id="a1d55-166">EAP-TLS를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="a1d55-166">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a1d55-167">SASL에는 TLS가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-167">SASL requires TLS.</span></span> <span data-ttu-id="a1d55-168">TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-168">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1d55-169">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="a1d55-169">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a1d55-170">필수</span><span class="sxs-lookup"><span data-stu-id="a1d55-170">Required</span></span></p></td>
<td><p><span data-ttu-id="a1d55-171">True</span><span class="sxs-lookup"><span data-stu-id="a1d55-171">True</span></span></p></td>
<td><p><span data-ttu-id="a1d55-172">TCP 전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="a1d55-172">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a1d55-173">SASL에는 TLS가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-173">SASL requires TLS.</span></span> <span data-ttu-id="a1d55-174">TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-174">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1d55-175">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="a1d55-175">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a1d55-176">필수</span><span class="sxs-lookup"><span data-stu-id="a1d55-176">Required</span></span></p></td>
<td><p><span data-ttu-id="a1d55-177">False</span><span class="sxs-lookup"><span data-stu-id="a1d55-177">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a1d55-178">유효 하지 않은 구성</span><span class="sxs-lookup"><span data-stu-id="a1d55-178">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a1d55-179">SASL에는 TLS가 필요 하 고 TLS는 사용할 수 없으므로 SASL/TLS가 제대로 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-179">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed.</span></span> <span data-ttu-id="a1d55-180">TCP 전화 접속 회의가 false로 설정 되었으며 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-180">TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1d55-181">필수</span><span class="sxs-lookup"><span data-stu-id="a1d55-181">Required</span></span></p></td>
<td><p><span data-ttu-id="a1d55-182">선택</span><span class="sxs-lookup"><span data-stu-id="a1d55-182">Optional</span></span></p></td>
<td><p><span data-ttu-id="a1d55-183">True</span><span class="sxs-lookup"><span data-stu-id="a1d55-183">True</span></span></p></td>
<td><p><span data-ttu-id="a1d55-184">EAP-TLS를 통한 SASL, TLS 전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="a1d55-184">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1d55-185">필수</span><span class="sxs-lookup"><span data-stu-id="a1d55-185">Required</span></span></p></td>
<td><p><span data-ttu-id="a1d55-186">선택</span><span class="sxs-lookup"><span data-stu-id="a1d55-186">Optional</span></span></p></td>
<td><p><span data-ttu-id="a1d55-187">False</span><span class="sxs-lookup"><span data-stu-id="a1d55-187">False</span></span></p></td>
<td><p><span data-ttu-id="a1d55-188">EAP-TLS를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="a1d55-188">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1d55-189">선택</span><span class="sxs-lookup"><span data-stu-id="a1d55-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="a1d55-190">선택</span><span class="sxs-lookup"><span data-stu-id="a1d55-190">Optional</span></span></p></td>
<td><p><span data-ttu-id="a1d55-191">True</span><span class="sxs-lookup"><span data-stu-id="a1d55-191">True</span></span></p></td>
<td><p><span data-ttu-id="a1d55-192">TLS, TLS 전화 접속 회의, TCP 전화 접속 회의을 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="a1d55-192">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a1d55-193">SASL에는 TLS가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-193">SASL requires TLS.</span></span> <span data-ttu-id="a1d55-194">TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-194">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1d55-195">선택</span><span class="sxs-lookup"><span data-stu-id="a1d55-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="a1d55-196">선택</span><span class="sxs-lookup"><span data-stu-id="a1d55-196">Optional</span></span></p></td>
<td><p><span data-ttu-id="a1d55-197">False</span><span class="sxs-lookup"><span data-stu-id="a1d55-197">False</span></span></p></td>
<td><p><span data-ttu-id="a1d55-198">EAP-TLS를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="a1d55-198">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a1d55-199">SASL에는 TLS가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-199">SASL requires TLS.</span></span> <span data-ttu-id="a1d55-200">TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-200">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1d55-201">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="a1d55-201">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a1d55-202">선택</span><span class="sxs-lookup"><span data-stu-id="a1d55-202">Optional</span></span></p></td>
<td><p><span data-ttu-id="a1d55-203">True</span><span class="sxs-lookup"><span data-stu-id="a1d55-203">True</span></span></p></td>
<td><p><span data-ttu-id="a1d55-204">TCP 전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="a1d55-204">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a1d55-205">SASL에는 TLS가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-205">SASL requires TLS.</span></span> <span data-ttu-id="a1d55-206">TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-206">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1d55-207">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="a1d55-207">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a1d55-208">선택</span><span class="sxs-lookup"><span data-stu-id="a1d55-208">Optional</span></span></p></td>
<td><p><span data-ttu-id="a1d55-209">False</span><span class="sxs-lookup"><span data-stu-id="a1d55-209">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a1d55-210">유효 하지 않은 구성</span><span class="sxs-lookup"><span data-stu-id="a1d55-210">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a1d55-211">SASL에는 TLS가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-211">SASL requires TLS.</span></span> <span data-ttu-id="a1d55-212">TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-212">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1d55-213">필수</span><span class="sxs-lookup"><span data-stu-id="a1d55-213">Required</span></span></p></td>
<td><p><span data-ttu-id="a1d55-214">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="a1d55-214">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a1d55-215">True</span><span class="sxs-lookup"><span data-stu-id="a1d55-215">True</span></span></p></td>
<td><p><span data-ttu-id="a1d55-216">TLS 전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="a1d55-216">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="a1d55-217">구성에서는 TLS 전화 접속 회의을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-217">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1d55-218">필수</span><span class="sxs-lookup"><span data-stu-id="a1d55-218">Required</span></span></p></td>
<td><p><span data-ttu-id="a1d55-219">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="a1d55-219">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a1d55-220">False</span><span class="sxs-lookup"><span data-stu-id="a1d55-220">False</span></span></p></td>
<td><p><span data-ttu-id="a1d55-221">유효 하지 않은 구성</span><span class="sxs-lookup"><span data-stu-id="a1d55-221">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a1d55-222">SASL 또는 전화 접속 회의을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-222">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1d55-223">선택</span><span class="sxs-lookup"><span data-stu-id="a1d55-223">Optional</span></span></p></td>
<td><p><span data-ttu-id="a1d55-224">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="a1d55-224">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a1d55-225">True</span><span class="sxs-lookup"><span data-stu-id="a1d55-225">True</span></span></p></td>
<td><p><span data-ttu-id="a1d55-226">TLS 전화 접속 회의, TCP 전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="a1d55-226">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="a1d55-227">다른 끝점의 협상 선택에 따라 TCP 또는 TLS 전화 접속 회의이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-227">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1d55-228">선택</span><span class="sxs-lookup"><span data-stu-id="a1d55-228">Optional</span></span></p></td>
<td><p><span data-ttu-id="a1d55-229">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="a1d55-229">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a1d55-230">False</span><span class="sxs-lookup"><span data-stu-id="a1d55-230">False</span></span></p></td>
<td><p><span data-ttu-id="a1d55-231">유효 하지 않은 구성</span><span class="sxs-lookup"><span data-stu-id="a1d55-231">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a1d55-232">SASL 또는 전화 접속 회의을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-232">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1d55-233">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="a1d55-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a1d55-234">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="a1d55-234">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a1d55-235">True</span><span class="sxs-lookup"><span data-stu-id="a1d55-235">True</span></span></p></td>
<td><p><span data-ttu-id="a1d55-236">TCP 전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="a1d55-236">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="a1d55-237">사용할 수 있는 유일한 협상 방법은 TCP 전화 접속 회의입니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-237">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1d55-238">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="a1d55-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a1d55-239">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="a1d55-239">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a1d55-240">False</span><span class="sxs-lookup"><span data-stu-id="a1d55-240">False</span></span></p></td>
<td><p><span data-ttu-id="a1d55-241">유효 하지 않은 구성</span><span class="sxs-lookup"><span data-stu-id="a1d55-241">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a1d55-242">SASL 또는 전화 접속 회의을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d55-242">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

