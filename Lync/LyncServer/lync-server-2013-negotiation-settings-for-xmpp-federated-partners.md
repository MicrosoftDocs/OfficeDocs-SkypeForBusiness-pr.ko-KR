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
ms.openlocfilehash: c190e4a45a70bd527aa8fc6323a671d481f04872
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="58aac-102">Lync Server 2013의 XMPP 페더레이션 파트너에 대 한 협상 설정</span><span class="sxs-lookup"><span data-stu-id="58aac-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58aac-103">_**마지막으로 수정 된 항목:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="58aac-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="58aac-104">XMPP 파트너 구성의 협상 유형에 대 한 설정은 다양 한 조합으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="58aac-105">이러한 모든 조합은 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="58aac-106">이 항목에서 설명 하는 표에서는 유효 하 고 유효 하지 않은 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="58aac-107">일반적인 구성에 대 한 자세한 내용은 두 번째 표에 나오는 모든 가능한 조합을 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="58aac-108">TLS ( *전송 계층 보안* )도 사용할 수 있는 **경우가 아니면** SASL ( *단순 인증 및 보안 계층* )을 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="58aac-109">SASL은 부호화 되지 않은 (읽을 수 있는) 형식으로 전송 되며 TLS와 같은 다른 방법으로 보호 되지 않으면 전송 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="58aac-110">일반 XMPP 페더레이션 협상 방법</span><span class="sxs-lookup"><span data-stu-id="58aac-110">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="58aac-111">TLS (전송 계층 보안)</span><span class="sxs-lookup"><span data-stu-id="58aac-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="58aac-112">SASL (Simple Authentication and Security Layer)</span><span class="sxs-lookup"><span data-stu-id="58aac-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="58aac-113">전화 접속 회의 인증</span><span class="sxs-lookup"><span data-stu-id="58aac-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="58aac-114">예상 인증 방법</span><span class="sxs-lookup"><span data-stu-id="58aac-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="58aac-115">Notes</span><span class="sxs-lookup"><span data-stu-id="58aac-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58aac-116">필수</span><span class="sxs-lookup"><span data-stu-id="58aac-116">Required</span></span></p></td>
<td><p><span data-ttu-id="58aac-117">필수</span><span class="sxs-lookup"><span data-stu-id="58aac-117">Required</span></span></p></td>
<td><p><span data-ttu-id="58aac-118">False</span><span class="sxs-lookup"><span data-stu-id="58aac-118">False</span></span></p></td>
<td><p><span data-ttu-id="58aac-119">EAP-TLS를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="58aac-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="58aac-120">TLS 및 SASL 필요한 경우 SASL 메시지 스트림이 안전한 지 확인 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-120">TLS and SASL required helps to ensure that the SASL message stream is secure.</span></span> <span data-ttu-id="58aac-121">XMPP 페더레이션 파트너가 TLS를 필수 또는 선택으로 설정 하지 않은 경우에는 전화 접속 회의을 사용할 수 없으며 대체 방법으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-121">Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58aac-122">필수</span><span class="sxs-lookup"><span data-stu-id="58aac-122">Required</span></span></p></td>
<td><p><span data-ttu-id="58aac-123">선택 사항</span><span class="sxs-lookup"><span data-stu-id="58aac-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="58aac-124">참</span><span class="sxs-lookup"><span data-stu-id="58aac-124">True</span></span></p></td>
<td><p><span data-ttu-id="58aac-125">TLS, TLS 전화 접속 회의, TCP 전화 접속 회의을 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="58aac-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="58aac-126">XMPP 페더레이션 파트너가 SASL을 optional로 설정 했거나 필요한 SASL을 사용 하는 경우 TLS를 요구 합니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-126">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used.</span></span> <span data-ttu-id="58aac-127">SASL을 사용할 수 없는 경우 전화 접속 회의 over TLS가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-127">If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58aac-128">선택</span><span class="sxs-lookup"><span data-stu-id="58aac-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="58aac-129">선택</span><span class="sxs-lookup"><span data-stu-id="58aac-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="58aac-130">참</span><span class="sxs-lookup"><span data-stu-id="58aac-130">True</span></span></p></td>
<td><p><span data-ttu-id="58aac-131">TLS, TLS 전화 접속 회의, TCP 전화 접속 회의을 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="58aac-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="58aac-132">협상 방법의 유연성이 매우 뛰어납니다, 이러한 설정은 XMPP 페더레이션 파트너의 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-132">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings.</span></span> <span data-ttu-id="58aac-133">파트너가 TLS 옵션 또는 필수를 포함 하지만 SASL이 지원 되지 않는 경우 TLS 전화 접속 회의를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-133">If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available.</span></span> <span data-ttu-id="58aac-134">파트너에 TLS 및 SASL이 optional 또는 required로 설정 되어 있으면 SASL을 통해 최적의 TLS 선택이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-134">If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58aac-135">미지원</span><span class="sxs-lookup"><span data-stu-id="58aac-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="58aac-136">미지원</span><span class="sxs-lookup"><span data-stu-id="58aac-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="58aac-137">참</span><span class="sxs-lookup"><span data-stu-id="58aac-137">True</span></span></p></td>
<td><p><span data-ttu-id="58aac-138">TCP 전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="58aac-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="58aac-139">대부분의 경우 TCP 전화 접속 회의은 유일한 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-139">In many cases, TCP Dialback is the only possible solution.</span></span> <span data-ttu-id="58aac-140">다른 옵션 보다 덜 바람직한 방법으로는 몇 가지 신뢰 수준이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-140">Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="58aac-141">XMPP 페더레이션 협상 방법 매트릭스-전체</span><span class="sxs-lookup"><span data-stu-id="58aac-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="58aac-142">TLS (전송 계층 보안)</span><span class="sxs-lookup"><span data-stu-id="58aac-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="58aac-143">SASL (Simple Authentication and Security Layer)</span><span class="sxs-lookup"><span data-stu-id="58aac-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="58aac-144">전화 접속 회의 인증</span><span class="sxs-lookup"><span data-stu-id="58aac-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="58aac-145">예상 인증 방법</span><span class="sxs-lookup"><span data-stu-id="58aac-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="58aac-146">유효 하지 않은 구성에 대 한 메모, 경고 또는 오류</span><span class="sxs-lookup"><span data-stu-id="58aac-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58aac-147">필수</span><span class="sxs-lookup"><span data-stu-id="58aac-147">Required</span></span></p></td>
<td><p><span data-ttu-id="58aac-148">필수</span><span class="sxs-lookup"><span data-stu-id="58aac-148">Required</span></span></p></td>
<td><p><span data-ttu-id="58aac-149">참</span><span class="sxs-lookup"><span data-stu-id="58aac-149">True</span></span></p></td>
<td><p><span data-ttu-id="58aac-150">EAP-TLS를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="58aac-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="58aac-151">SASL 및 TLS가 필요한 경우에는 전화 접속 회의가 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58aac-152">필수</span><span class="sxs-lookup"><span data-stu-id="58aac-152">Required</span></span></p></td>
<td><p><span data-ttu-id="58aac-153">필수</span><span class="sxs-lookup"><span data-stu-id="58aac-153">Required</span></span></p></td>
<td><p><span data-ttu-id="58aac-154">False</span><span class="sxs-lookup"><span data-stu-id="58aac-154">False</span></span></p></td>
<td><p><span data-ttu-id="58aac-155">EAP-TLS를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="58aac-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58aac-156">선택</span><span class="sxs-lookup"><span data-stu-id="58aac-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="58aac-157">필수</span><span class="sxs-lookup"><span data-stu-id="58aac-157">Required</span></span></p></td>
<td><p><span data-ttu-id="58aac-158">참</span><span class="sxs-lookup"><span data-stu-id="58aac-158">True</span></span></p></td>
<td><p><span data-ttu-id="58aac-159">TLS, TLS 전화 접속 회의, TCP 전화 접속 회의을 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="58aac-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="58aac-160">SASL에는 TLS가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-160">SASL requires TLS.</span></span> <span data-ttu-id="58aac-161">TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-161">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58aac-162">선택</span><span class="sxs-lookup"><span data-stu-id="58aac-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="58aac-163">필수</span><span class="sxs-lookup"><span data-stu-id="58aac-163">Required</span></span></p></td>
<td><p><span data-ttu-id="58aac-164">False</span><span class="sxs-lookup"><span data-stu-id="58aac-164">False</span></span></p></td>
<td><p><span data-ttu-id="58aac-165">EAP-TLS를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="58aac-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="58aac-166">SASL에는 TLS가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-166">SASL requires TLS.</span></span> <span data-ttu-id="58aac-167">TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-167">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58aac-168">미지원</span><span class="sxs-lookup"><span data-stu-id="58aac-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="58aac-169">필수</span><span class="sxs-lookup"><span data-stu-id="58aac-169">Required</span></span></p></td>
<td><p><span data-ttu-id="58aac-170">참</span><span class="sxs-lookup"><span data-stu-id="58aac-170">True</span></span></p></td>
<td><p><span data-ttu-id="58aac-171">TCP 전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="58aac-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="58aac-172">SASL에는 TLS가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-172">SASL requires TLS.</span></span> <span data-ttu-id="58aac-173">TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-173">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58aac-174">미지원</span><span class="sxs-lookup"><span data-stu-id="58aac-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="58aac-175">필수</span><span class="sxs-lookup"><span data-stu-id="58aac-175">Required</span></span></p></td>
<td><p><span data-ttu-id="58aac-176">False</span><span class="sxs-lookup"><span data-stu-id="58aac-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="58aac-177">유효 하지 않은 구성</span><span class="sxs-lookup"><span data-stu-id="58aac-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="58aac-178">SASL에는 TLS가 필요 하 고 TLS는 사용할 수 없으므로 SASL/TLS가 제대로 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-178">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed.</span></span> <span data-ttu-id="58aac-179">TCP 전화 접속 회의가 false로 설정 되었으며 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-179">TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58aac-180">필수</span><span class="sxs-lookup"><span data-stu-id="58aac-180">Required</span></span></p></td>
<td><p><span data-ttu-id="58aac-181">선택 사항</span><span class="sxs-lookup"><span data-stu-id="58aac-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="58aac-182">참</span><span class="sxs-lookup"><span data-stu-id="58aac-182">True</span></span></p></td>
<td><p><span data-ttu-id="58aac-183">EAP-TLS를 통한 SASL, TLS 전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="58aac-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58aac-184">필수</span><span class="sxs-lookup"><span data-stu-id="58aac-184">Required</span></span></p></td>
<td><p><span data-ttu-id="58aac-185">선택 사항</span><span class="sxs-lookup"><span data-stu-id="58aac-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="58aac-186">False</span><span class="sxs-lookup"><span data-stu-id="58aac-186">False</span></span></p></td>
<td><p><span data-ttu-id="58aac-187">EAP-TLS를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="58aac-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58aac-188">선택</span><span class="sxs-lookup"><span data-stu-id="58aac-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="58aac-189">선택</span><span class="sxs-lookup"><span data-stu-id="58aac-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="58aac-190">참</span><span class="sxs-lookup"><span data-stu-id="58aac-190">True</span></span></p></td>
<td><p><span data-ttu-id="58aac-191">TLS, TLS 전화 접속 회의, TCP 전화 접속 회의을 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="58aac-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="58aac-192">SASL에는 TLS가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-192">SASL requires TLS.</span></span> <span data-ttu-id="58aac-193">TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-193">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58aac-194">선택</span><span class="sxs-lookup"><span data-stu-id="58aac-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="58aac-195">선택</span><span class="sxs-lookup"><span data-stu-id="58aac-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="58aac-196">False</span><span class="sxs-lookup"><span data-stu-id="58aac-196">False</span></span></p></td>
<td><p><span data-ttu-id="58aac-197">EAP-TLS를 통한 SASL</span><span class="sxs-lookup"><span data-stu-id="58aac-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="58aac-198">SASL에는 TLS가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-198">SASL requires TLS.</span></span> <span data-ttu-id="58aac-199">TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-199">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58aac-200">미지원</span><span class="sxs-lookup"><span data-stu-id="58aac-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="58aac-201">선택</span><span class="sxs-lookup"><span data-stu-id="58aac-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="58aac-202">참</span><span class="sxs-lookup"><span data-stu-id="58aac-202">True</span></span></p></td>
<td><p><span data-ttu-id="58aac-203">TCP 전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="58aac-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="58aac-204">SASL에는 TLS가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-204">SASL requires TLS.</span></span> <span data-ttu-id="58aac-205">TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-205">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58aac-206">미지원</span><span class="sxs-lookup"><span data-stu-id="58aac-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="58aac-207">선택</span><span class="sxs-lookup"><span data-stu-id="58aac-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="58aac-208">False</span><span class="sxs-lookup"><span data-stu-id="58aac-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="58aac-209">유효 하지 않은 구성</span><span class="sxs-lookup"><span data-stu-id="58aac-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="58aac-210">SASL에는 TLS가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-210">SASL requires TLS.</span></span> <span data-ttu-id="58aac-211">TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-211">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58aac-212">필수</span><span class="sxs-lookup"><span data-stu-id="58aac-212">Required</span></span></p></td>
<td><p><span data-ttu-id="58aac-213">미지원</span><span class="sxs-lookup"><span data-stu-id="58aac-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="58aac-214">참</span><span class="sxs-lookup"><span data-stu-id="58aac-214">True</span></span></p></td>
<td><p><span data-ttu-id="58aac-215">TLS 전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="58aac-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="58aac-216">구성에서는 TLS 전화 접속 회의을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58aac-217">필수</span><span class="sxs-lookup"><span data-stu-id="58aac-217">Required</span></span></p></td>
<td><p><span data-ttu-id="58aac-218">미지원</span><span class="sxs-lookup"><span data-stu-id="58aac-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="58aac-219">False</span><span class="sxs-lookup"><span data-stu-id="58aac-219">False</span></span></p></td>
<td><p><span data-ttu-id="58aac-220">유효 하지 않은 구성</span><span class="sxs-lookup"><span data-stu-id="58aac-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="58aac-221">SASL 또는 전화 접속 회의을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58aac-222">선택</span><span class="sxs-lookup"><span data-stu-id="58aac-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="58aac-223">미지원</span><span class="sxs-lookup"><span data-stu-id="58aac-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="58aac-224">참</span><span class="sxs-lookup"><span data-stu-id="58aac-224">True</span></span></p></td>
<td><p><span data-ttu-id="58aac-225">TLS 전화 접속 회의, TCP 전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="58aac-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="58aac-226">다른 끝점의 협상 선택에 따라 TCP 또는 TLS 전화 접속 회의이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58aac-227">선택</span><span class="sxs-lookup"><span data-stu-id="58aac-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="58aac-228">미지원</span><span class="sxs-lookup"><span data-stu-id="58aac-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="58aac-229">False</span><span class="sxs-lookup"><span data-stu-id="58aac-229">False</span></span></p></td>
<td><p><span data-ttu-id="58aac-230">유효 하지 않은 구성</span><span class="sxs-lookup"><span data-stu-id="58aac-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="58aac-231">SASL 또는 전화 접속 회의을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58aac-232">미지원</span><span class="sxs-lookup"><span data-stu-id="58aac-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="58aac-233">미지원</span><span class="sxs-lookup"><span data-stu-id="58aac-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="58aac-234">참</span><span class="sxs-lookup"><span data-stu-id="58aac-234">True</span></span></p></td>
<td><p><span data-ttu-id="58aac-235">TCP 전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="58aac-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="58aac-236">사용할 수 있는 유일한 협상 방법은 TCP 전화 접속 회의입니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58aac-237">미지원</span><span class="sxs-lookup"><span data-stu-id="58aac-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="58aac-238">미지원</span><span class="sxs-lookup"><span data-stu-id="58aac-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="58aac-239">False</span><span class="sxs-lookup"><span data-stu-id="58aac-239">False</span></span></p></td>
<td><p><span data-ttu-id="58aac-240">유효 하지 않은 구성</span><span class="sxs-lookup"><span data-stu-id="58aac-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="58aac-241">SASL 또는 전화 접속 회의을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58aac-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

