---
title: 'Lync Server 2013: XMPP 페더레이션 파트너에 대 한 협상 설정'
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
ms.openlocfilehash: bdb09d52970b5fd97395acda6a2e4fbc824a378d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505595"
---
# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="14c72-102">Lync Server 2013의 XMPP 페더레이션 파트너에 대 한 협상 설정</span><span class="sxs-lookup"><span data-stu-id="14c72-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14c72-103">_**마지막으로 수정 된 항목:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="14c72-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="14c72-104">XMPP 파트너 구성의 협상 유형에 대 한 설정은 다양 한 조합으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="14c72-105">이러한 모든 조합은 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="14c72-106">이 항목에서 설명 하는 표에서는 유효 하 고 유효 하지 않은 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="14c72-107">일반적인 구성에 대 한 자세한 내용은 두 번째 표에 나오는 모든 가능한 조합을 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="14c72-108">TLS ( *전송 계층 보안* )도 사용할 수 있는 **경우가 아니면** SASL ( *단순 인증 및 보안 계층* )을 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="14c72-109">SASL은 부호화 되지 않은 (읽을 수 있는) 형식으로 전송 되며 TLS와 같은 다른 방법으로 보호 되지 않으면 전송 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="14c72-110">일반 XMPP 페더레이션 협상 방법</span><span class="sxs-lookup"><span data-stu-id="14c72-110">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="14c72-111">TLS (전송 계층 보안)</span><span class="sxs-lookup"><span data-stu-id="14c72-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="14c72-112">SASL (Simple Authentication and Security Layer)</span><span class="sxs-lookup"><span data-stu-id="14c72-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="14c72-113">전화 접속 회의 인증</span><span class="sxs-lookup"><span data-stu-id="14c72-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="14c72-114">예상 인증 방법</span><span class="sxs-lookup"><span data-stu-id="14c72-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="14c72-115">참고</span><span class="sxs-lookup"><span data-stu-id="14c72-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14c72-116">필수</span><span class="sxs-lookup"><span data-stu-id="14c72-116">Required</span></span></p></td>
<td><p><span data-ttu-id="14c72-117">필수</span><span class="sxs-lookup"><span data-stu-id="14c72-117">Required</span></span></p></td>
<td><p><span data-ttu-id="14c72-118">False</span><span class="sxs-lookup"><span data-stu-id="14c72-118">False</span></span></p></td>
<td><p><span data-ttu-id="14c72-119">EAP-TLS를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="14c72-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="14c72-120">TLS 및 SASL 필요한 경우 SASL 메시지 스트림이 안전한 지 확인 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-120">TLS and SASL required helps to ensure that the SASL message stream is secure.</span></span> <span data-ttu-id="14c72-121">XMPP 페더레이션 파트너가 TLS를 필수 또는 선택으로 설정 하지 않은 경우에는 전화 접속 회의을 사용할 수 없으며 대체 방법으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-121">Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14c72-122">필수</span><span class="sxs-lookup"><span data-stu-id="14c72-122">Required</span></span></p></td>
<td><p><span data-ttu-id="14c72-123">선택</span><span class="sxs-lookup"><span data-stu-id="14c72-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="14c72-124">True</span><span class="sxs-lookup"><span data-stu-id="14c72-124">True</span></span></p></td>
<td><p><span data-ttu-id="14c72-125">TLS, TLS 전화 접속 회의, TCP 전화 접속 회의을 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="14c72-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="14c72-126">XMPP 페더레이션 파트너가 SASL을 optional로 설정 했거나 필요한 SASL을 사용 하는 경우 TLS를 요구 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-126">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used.</span></span> <span data-ttu-id="14c72-127">SASL을 사용할 수 없는 경우 전화 접속 회의 over TLS가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-127">If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14c72-128">선택</span><span class="sxs-lookup"><span data-stu-id="14c72-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="14c72-129">선택</span><span class="sxs-lookup"><span data-stu-id="14c72-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="14c72-130">True</span><span class="sxs-lookup"><span data-stu-id="14c72-130">True</span></span></p></td>
<td><p><span data-ttu-id="14c72-131">TLS, TLS 전화 접속 회의, TCP 전화 접속 회의을 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="14c72-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="14c72-132">협상 방법의 유연성이 매우 뛰어납니다, 이러한 설정은 XMPP 페더레이션 파트너의 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-132">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings.</span></span> <span data-ttu-id="14c72-133">파트너가 TLS 옵션 또는 필수를 포함 하지만 SASL이 지원 되지 않는 경우 TLS 전화 접속 회의를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-133">If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available.</span></span> <span data-ttu-id="14c72-134">파트너에 TLS 및 SASL이 optional 또는 required로 설정 되어 있으면 SASL을 통해 최적의 TLS 선택이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-134">If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14c72-135">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="14c72-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="14c72-136">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="14c72-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="14c72-137">True</span><span class="sxs-lookup"><span data-stu-id="14c72-137">True</span></span></p></td>
<td><p><span data-ttu-id="14c72-138">TCP 전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="14c72-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="14c72-139">대부분의 경우 TCP 전화 접속 회의은 유일한 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-139">In many cases, TCP Dialback is the only possible solution.</span></span> <span data-ttu-id="14c72-140">다른 옵션 보다 덜 바람직한 방법으로는 몇 가지 신뢰 수준이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-140">Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="14c72-141">XMPP 페더레이션 협상 방법 매트릭스-전체</span><span class="sxs-lookup"><span data-stu-id="14c72-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="14c72-142">TLS (전송 계층 보안)</span><span class="sxs-lookup"><span data-stu-id="14c72-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="14c72-143">SASL (Simple Authentication and Security Layer)</span><span class="sxs-lookup"><span data-stu-id="14c72-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="14c72-144">전화 접속 회의 인증</span><span class="sxs-lookup"><span data-stu-id="14c72-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="14c72-145">예상 인증 방법</span><span class="sxs-lookup"><span data-stu-id="14c72-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="14c72-146">유효 하지 않은 구성에 대 한 메모, 경고 또는 오류</span><span class="sxs-lookup"><span data-stu-id="14c72-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14c72-147">필수</span><span class="sxs-lookup"><span data-stu-id="14c72-147">Required</span></span></p></td>
<td><p><span data-ttu-id="14c72-148">필수</span><span class="sxs-lookup"><span data-stu-id="14c72-148">Required</span></span></p></td>
<td><p><span data-ttu-id="14c72-149">True</span><span class="sxs-lookup"><span data-stu-id="14c72-149">True</span></span></p></td>
<td><p><span data-ttu-id="14c72-150">EAP-TLS를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="14c72-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="14c72-151">SASL 및 TLS가 필요한 경우에는 전화 접속 회의가 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14c72-152">필수</span><span class="sxs-lookup"><span data-stu-id="14c72-152">Required</span></span></p></td>
<td><p><span data-ttu-id="14c72-153">필수</span><span class="sxs-lookup"><span data-stu-id="14c72-153">Required</span></span></p></td>
<td><p><span data-ttu-id="14c72-154">False</span><span class="sxs-lookup"><span data-stu-id="14c72-154">False</span></span></p></td>
<td><p><span data-ttu-id="14c72-155">EAP-TLS를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="14c72-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14c72-156">선택</span><span class="sxs-lookup"><span data-stu-id="14c72-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="14c72-157">필수</span><span class="sxs-lookup"><span data-stu-id="14c72-157">Required</span></span></p></td>
<td><p><span data-ttu-id="14c72-158">True</span><span class="sxs-lookup"><span data-stu-id="14c72-158">True</span></span></p></td>
<td><p><span data-ttu-id="14c72-159">TLS, TLS 전화 접속 회의, TCP 전화 접속 회의을 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="14c72-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="14c72-160">SASL에는 TLS가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-160">SASL requires TLS.</span></span> <span data-ttu-id="14c72-161">TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-161">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14c72-162">선택</span><span class="sxs-lookup"><span data-stu-id="14c72-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="14c72-163">필수</span><span class="sxs-lookup"><span data-stu-id="14c72-163">Required</span></span></p></td>
<td><p><span data-ttu-id="14c72-164">False</span><span class="sxs-lookup"><span data-stu-id="14c72-164">False</span></span></p></td>
<td><p><span data-ttu-id="14c72-165">EAP-TLS를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="14c72-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="14c72-166">SASL에는 TLS가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-166">SASL requires TLS.</span></span> <span data-ttu-id="14c72-167">TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-167">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14c72-168">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="14c72-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="14c72-169">필수</span><span class="sxs-lookup"><span data-stu-id="14c72-169">Required</span></span></p></td>
<td><p><span data-ttu-id="14c72-170">True</span><span class="sxs-lookup"><span data-stu-id="14c72-170">True</span></span></p></td>
<td><p><span data-ttu-id="14c72-171">TCP 전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="14c72-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="14c72-172">SASL에는 TLS가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-172">SASL requires TLS.</span></span> <span data-ttu-id="14c72-173">TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-173">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14c72-174">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="14c72-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="14c72-175">필수</span><span class="sxs-lookup"><span data-stu-id="14c72-175">Required</span></span></p></td>
<td><p><span data-ttu-id="14c72-176">False</span><span class="sxs-lookup"><span data-stu-id="14c72-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="14c72-177">유효 하지 않은 구성</span><span class="sxs-lookup"><span data-stu-id="14c72-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="14c72-178">SASL에는 TLS가 필요 하 고 TLS는 사용할 수 없으므로 SASL/TLS가 제대로 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-178">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed.</span></span> <span data-ttu-id="14c72-179">TCP 전화 접속 회의가 false로 설정 되었으며 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-179">TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14c72-180">필수</span><span class="sxs-lookup"><span data-stu-id="14c72-180">Required</span></span></p></td>
<td><p><span data-ttu-id="14c72-181">선택</span><span class="sxs-lookup"><span data-stu-id="14c72-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="14c72-182">True</span><span class="sxs-lookup"><span data-stu-id="14c72-182">True</span></span></p></td>
<td><p><span data-ttu-id="14c72-183">EAP-TLS를 통한 SASL, TLS 전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="14c72-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14c72-184">필수</span><span class="sxs-lookup"><span data-stu-id="14c72-184">Required</span></span></p></td>
<td><p><span data-ttu-id="14c72-185">선택</span><span class="sxs-lookup"><span data-stu-id="14c72-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="14c72-186">False</span><span class="sxs-lookup"><span data-stu-id="14c72-186">False</span></span></p></td>
<td><p><span data-ttu-id="14c72-187">EAP-TLS를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="14c72-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14c72-188">선택</span><span class="sxs-lookup"><span data-stu-id="14c72-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="14c72-189">선택</span><span class="sxs-lookup"><span data-stu-id="14c72-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="14c72-190">True</span><span class="sxs-lookup"><span data-stu-id="14c72-190">True</span></span></p></td>
<td><p><span data-ttu-id="14c72-191">TLS, TLS 전화 접속 회의, TCP 전화 접속 회의을 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="14c72-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="14c72-192">SASL에는 TLS가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-192">SASL requires TLS.</span></span> <span data-ttu-id="14c72-193">TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-193">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14c72-194">선택</span><span class="sxs-lookup"><span data-stu-id="14c72-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="14c72-195">선택</span><span class="sxs-lookup"><span data-stu-id="14c72-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="14c72-196">False</span><span class="sxs-lookup"><span data-stu-id="14c72-196">False</span></span></p></td>
<td><p><span data-ttu-id="14c72-197">EAP-TLS를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="14c72-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="14c72-198">SASL에는 TLS가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-198">SASL requires TLS.</span></span> <span data-ttu-id="14c72-199">TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-199">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14c72-200">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="14c72-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="14c72-201">선택</span><span class="sxs-lookup"><span data-stu-id="14c72-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="14c72-202">True</span><span class="sxs-lookup"><span data-stu-id="14c72-202">True</span></span></p></td>
<td><p><span data-ttu-id="14c72-203">TCP 전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="14c72-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="14c72-204">SASL에는 TLS가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-204">SASL requires TLS.</span></span> <span data-ttu-id="14c72-205">TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-205">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14c72-206">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="14c72-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="14c72-207">선택</span><span class="sxs-lookup"><span data-stu-id="14c72-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="14c72-208">False</span><span class="sxs-lookup"><span data-stu-id="14c72-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="14c72-209">유효 하지 않은 구성</span><span class="sxs-lookup"><span data-stu-id="14c72-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="14c72-210">SASL에는 TLS가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-210">SASL requires TLS.</span></span> <span data-ttu-id="14c72-211">TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-211">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14c72-212">필수</span><span class="sxs-lookup"><span data-stu-id="14c72-212">Required</span></span></p></td>
<td><p><span data-ttu-id="14c72-213">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="14c72-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="14c72-214">True</span><span class="sxs-lookup"><span data-stu-id="14c72-214">True</span></span></p></td>
<td><p><span data-ttu-id="14c72-215">TLS 전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="14c72-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="14c72-216">구성에서는 TLS 전화 접속 회의을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14c72-217">필수</span><span class="sxs-lookup"><span data-stu-id="14c72-217">Required</span></span></p></td>
<td><p><span data-ttu-id="14c72-218">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="14c72-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="14c72-219">False</span><span class="sxs-lookup"><span data-stu-id="14c72-219">False</span></span></p></td>
<td><p><span data-ttu-id="14c72-220">유효 하지 않은 구성</span><span class="sxs-lookup"><span data-stu-id="14c72-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="14c72-221">SASL 또는 전화 접속 회의을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14c72-222">선택</span><span class="sxs-lookup"><span data-stu-id="14c72-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="14c72-223">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="14c72-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="14c72-224">True</span><span class="sxs-lookup"><span data-stu-id="14c72-224">True</span></span></p></td>
<td><p><span data-ttu-id="14c72-225">TLS 전화 접속 회의, TCP 전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="14c72-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="14c72-226">다른 끝점의 협상 선택에 따라 TCP 또는 TLS 전화 접속 회의이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14c72-227">선택</span><span class="sxs-lookup"><span data-stu-id="14c72-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="14c72-228">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="14c72-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="14c72-229">False</span><span class="sxs-lookup"><span data-stu-id="14c72-229">False</span></span></p></td>
<td><p><span data-ttu-id="14c72-230">유효 하지 않은 구성</span><span class="sxs-lookup"><span data-stu-id="14c72-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="14c72-231">SASL 또는 전화 접속 회의을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14c72-232">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="14c72-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="14c72-233">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="14c72-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="14c72-234">True</span><span class="sxs-lookup"><span data-stu-id="14c72-234">True</span></span></p></td>
<td><p><span data-ttu-id="14c72-235">TCP 전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="14c72-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="14c72-236">사용할 수 있는 유일한 협상 방법은 TCP 전화 접속 회의입니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14c72-237">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="14c72-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="14c72-238">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="14c72-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="14c72-239">False</span><span class="sxs-lookup"><span data-stu-id="14c72-239">False</span></span></p></td>
<td><p><span data-ttu-id="14c72-240">유효 하지 않은 구성</span><span class="sxs-lookup"><span data-stu-id="14c72-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="14c72-241">SASL 또는 전화 접속 회의을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c72-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

