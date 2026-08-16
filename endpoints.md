---
layout: default
title: Endpoints
nav_order: 2
---

# 🔌 Endpoints

En esta sección se listan los endpoints disponibles en el microservicio de analíticas.

Esta página sirve como referencia estática para garantizar el acceso a los contratos de la API de forma rápida y clara.

## Listado de Endpoints

A continuación, haz clic en cada bloque para desplegar los detalles de la petición, parámetros y respuestas.

<details>
  <summary style="font-size: 1.1em; cursor: pointer; padding: 10px; background-color: #f8f9fa; border-radius: 4px; border-left: 4px solid #007bff; margin-bottom: 5px;">
    <strong style="color: #007bff;">GET</strong> <code>/api/v1/metricas/health</code> - Health Check
  </summary>
  <div style="padding: 15px; border: 1px solid #f8f9fa; border-top: none; margin-bottom: 20px;">
    
    <p><strong>ID de la Operación:</strong> <code>health_check_api_v1_metricas_health_get</code></p>
    
    <p>Endpoint de comprobación de estado de salud del microservicio.</p>

    <h3>Respuestas</h3>

    <p><strong>Código:</strong> <code>200 OK</code></p>
    <ul>
      <li><strong>Descripción:</strong> Successful Response</li>
    </ul>

    <div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{}</span>
</code></pre></div></div>

  </div>
</details>

<details>
  <summary style="font-size: 1.1em; cursor: pointer; padding: 10px; background-color: #f8f9fa; border-radius: 4px; border-left: 4px solid #007bff; margin-bottom: 5px;">
    <strong style="color: #007bff;">GET</strong> <code>/api/v1/metricas/disciplinas/top</code> - Top Disciplinas
  </summary>
  <div style="padding: 15px; border: 1px solid #f8f9fa; border-top: none; margin-bottom: 20px;">
    
    <p><strong>ID de la Operación:</strong> <code>top_disciplinas_api_v1_metricas_disciplinas_top_get</code></p>
    
    <p>Ranking de disciplinas con más inscriptos activos. Por defecto devuelve el top 5.</p>

    <h3>Parámetros de consulta (Query Params)</h3>
    <table>
      <thead>
        <tr>
          <th>Nombre</th>
          <th>Tipo</th>
          <th>Obligatorio</th>
          <th>Descripción</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><code>limite</code></td>
          <td>Integer</td>
          <td>No (Por defecto: 5)</td>
          <td>Cantidad de disciplinas a mostrar (Min: 1, Max: 20)</td>
        </tr>
      </tbody>
    </table>

    <h3>Respuestas</h3>

    <p><strong>Código:</strong> <code>200 OK</code></p>
    <ul>
      <li><strong>Descripción:</strong> Successful Response</li>
    </ul>
    <div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
  </span><span class="nl">"ranking"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
    </span><span class="p">{</span><span class="w">
      </span><span class="nl">"id"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="p">,</span><span class="w">
      </span><span class="nl">"nombre"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="p">,</span><span class="w">
      </span><span class="nl">"cupo_maximo"</span><span class="p">:</span><span class="w"> </span><span class="mi">0</span><span class="p">,</span><span class="w">
      </span><span class="nl">"total_inscriptos"</span><span class="p">:</span><span class="w"> </span><span class="mi">0</span><span class="p">,</span><span class="w">
      </span><span class="nl">"porcentaje_cupo"</span><span class="p">:</span><span class="w"> </span><span class="mf">0.0</span><span class="w">
    </span><span class="p">}</span><span class="w">
  </span><span class="p">],</span><span class="w">
  </span><span class="nl">"total"</span><span class="p">:</span><span class="w"> </span><span class="mi">0</span><span class="w">
</span><span class="p">}</span>
</code></pre></div></div>

    <p><strong>Código:</strong> <code>422 Unprocessable Entity</code></p>
    <ul>
      <li><strong>Descripción:</strong> Validation Error</li>
    </ul>
  </div>
</details>

<details>
  <summary style="font-size: 1.1em; cursor: pointer; padding: 10px; background-color: #f8f9fa; border-radius: 4px; border-left: 4px solid #007bff; margin-bottom: 5px;">
    <strong style="color: #007bff;">GET</strong> <code>/api/v1/metricas/instalaciones/ocupacion</code> - Ocupacion Instalaciones
  </summary>
  <div style="padding: 15px; border: 1px solid #f8f9fa; border-top: none; margin-bottom: 20px;">
    
    <p><strong>ID de la Operación:</strong> <code>ocupacion_instalaciones_api_v1_metricas_instalaciones_ocupacion_get</code></p>
    
    <p>Porcentaje de ocupación de instalaciones activas. Calcula horas reservadas / horas disponibles en el período.</p>

    <h3>Parámetros de consulta (Query Params)</h3>
    <table>
      <thead>
        <tr>
          <th>Nombre</th>
          <th>Tipo</th>
          <th>Obligatorio</th>
          <th>Descripción</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><code>dias</code></td>
          <td>Integer</td>
          <td>No (Por defecto: 30)</td>
          <td>Período en días para calcular (Min: 1, Max: 365)</td>
        </tr>
        <tr>
          <td><code>horas_diarias</code></td>
          <td>Integer</td>
          <td>No (Por defecto: 14)</td>
          <td>Horas operativas por día (Min: 1, Max: 24)</td>
        </tr>
      </tbody>
    </table>

    <h3>Respuestas</h3>

    <p><strong>Código:</strong> <code>200 OK</code></p>
    <ul>
      <li><strong>Descripción:</strong> Successful Response</li>
    </ul>
    <div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
  </span><span class="nl">"instalaciones"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
    </span><span class="p">{</span><span class="w">
      </span><span class="nl">"id"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="p">,</span><span class="w">
      </span><span class="nl">"nombre"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="p">,</span><span class="w">
      </span><span class="nl">"tipo"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="p">,</span><span class="w">
      </span><span class="nl">"horas_reservadas"</span><span class="p">:</span><span class="w"> </span><span class="mf">0.0</span><span class="p">,</span><span class="w">
      </span><span class="nl">"horas_disponibles"</span><span class="p">:</span><span class="w"> </span><span class="mi">0</span><span class="p">,</span><span class="w">
      </span><span class="nl">"porcentaje_ocupacion"</span><span class="p">:</span><span class="w"> </span><span class="mf">0.0</span><span class="w">
    </span><span class="p">}</span><span class="w">
  </span><span class="p">],</span><span class="w">
  </span><span class="nl">"total"</span><span class="p">:</span><span class="w"> </span><span class="mi">0</span><span class="p">,</span><span class="w">
  </span><span class="nl">"promedio_ocupacion"</span><span class="p">:</span><span class="w"> </span><span class="mf">0.0</span><span class="p">,</span><span class="w">
  </span><span class="nl">"periodo_dias"</span><span class="p">:</span><span class="w"> </span><span class="mi">0</span><span class="w">
</span><span class="p">}</span>
</code></pre></div></div>

    <p><strong>Código:</strong> <code>422 Unprocessable Entity</code></p>
    <ul>
      <li><strong>Descripción:</strong> Validation Error</li>
    </ul>
  </div>
</details>

<details>
  <summary style="font-size: 1.1em; cursor: pointer; padding: 10px; background-color: #f8f9fa; border-radius: 4px; border-left: 4px solid #007bff; margin-bottom: 5px;">
    <strong style="color: #007bff;">GET</strong> <code>/api/v1/metricas/eventos/top</code> - Top Eventos
  </summary>
  <div style="padding: 15px; border: 1px solid #f8f9fa; border-top: none; margin-bottom: 20px;">
    
    <p><strong>ID de la Operación:</strong> <code>top_eventos_api_v1_metricas_eventos_top_get</code></p>
    
    <p>Ranking de eventos por entradas vendidas y porcentaje de ocupación. Por defecto devuelve el top 5.</p>

    <h3>Parámetros de consulta (Query Params)</h3>
    <table>
      <thead>
        <tr>
          <th>Nombre</th>
          <th>Tipo</th>
          <th>Obligatorio</th>
          <th>Descripción</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><code>limite</code></td>
          <td>Integer</td>
          <td>No (Por defecto: 5)</td>
          <td>Cantidad de eventos a mostrar (Min: 1, Max: 20)</td>
        </tr>
      </tbody>
    </table>

    <h3>Respuestas</h3>

    <p><strong>Código:</strong> <code>200 OK</code></p>
    <ul>
      <li><strong>Descripción:</strong> Successful Response</li>
    </ul>
    <div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
  </span><span class="nl">"ranking"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
    </span><span class="p">{</span><span class="w">
      </span><span class="nl">"id"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="p">,</span><span class="w">
      </span><span class="nl">"nombre"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="p">,</span><span class="w">
      </span><span class="nl">"capacidad_maxima"</span><span class="p">:</span><span class="w"> </span><span class="mi">0</span><span class="p">,</span><span class="w">
      </span><span class="nl">"entradas_vendidas"</span><span class="p">:</span><span class="w"> </span><span class="mi">0</span><span class="p">,</span><span class="w">
      </span><span class="nl">"porcentaje_ocupacion"</span><span class="p">:</span><span class="w"> </span><span class="mf">0.0</span><span class="w">
    </span><span class="p">}</span><span class="w">
  </span><span class="p">],</span><span class="w">
  </span><span class="nl">"total"</span><span class="p">:</span><span class="w"> </span><span class="mi">0</span><span class="w">
</span><span class="p">}</span>
</code></pre></div></div>

    <p><strong>Código:</strong> <code>422 Unprocessable Entity</code></p>
    <ul>
      <li><strong>Descripción:</strong> Validation Error</li>
    </ul>
  </div>
</details>

<details>
  <summary style="font-size: 1.1em; cursor: pointer; padding: 10px; background-color: #f8f9fa; border-radius: 4px; border-left: 4px solid #007bff; margin-bottom: 5px;">
    <strong style="color: #007bff;">GET</strong> <code>/api/v1/metricas/productos/top</code> - Top Productos
  </summary>
  <div style="padding: 15px; border: 1px solid #f8f9fa; border-top: none; margin-bottom: 20px;">
    
    <p><strong>ID de la Operación:</strong> <code>top_productos_api_v1_metricas_productos_top_get</code></p>
    
    <p>Ranking de productos más vendidos por unidades y facturación. Por defecto devuelve el top 5.</p>

    <h3>Parámetros de consulta (Query Params)</h3>
    <table>
      <thead>
        <tr>
          <th>Nombre</th>
          <th>Tipo</th>
          <th>Obligatorio</th>
          <th>Descripción</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><code>limite</code></td>
          <td>Integer</td>
          <td>No (Por defecto: 5)</td>
          <td>Cantidad de productos a mostrar (Min: 1, Max: 20)</td>
        </tr>
      </tbody>
    </table>

    <h3>Respuestas</h3>

    <p><strong>Código:</strong> <code>200 OK</code></p>
    <ul>
      <li><strong>Descripción:</strong> Successful Response</li>
    </ul>
    <div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
  </span><span class="nl">"ranking"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
    </span><span class="p">{</span><span class="w">
      </span><span class="nl">"id"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="p">,</span><span class="w">
      </span><span class="nl">"nombre"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="p">,</span><span class="w">
      </span><span class="nl">"cantidad_vendida"</span><span class="p">:</span><span class="w"> </span><span class="mi">0</span><span class="p">,</span><span class="w">
      </span><span class="nl">"monto_total"</span><span class="p">:</span><span class="w"> </span><span class="mf">0.0</span><span class="w">
    </span><span class="p">}</span><span class="w">
  </span><span class="p">],</span><span class="w">
  </span><span class="nl">"total"</span><span class="p">:</span><span class="w"> </span><span class="mi">0</span><span class="w">
</span><span class="p">}</span>
</code></pre></div></div>

    <p><strong>Código:</strong> <code>422 Unprocessable Entity</code></p>
    <ul>
      <li><strong>Descripción:</strong> Validation Error</li>
    </ul>
  </div>
</details>

<details>
  <summary style="font-size: 1.1em; cursor: pointer; padding: 10px; background-color: #f8f9fa; border-radius: 4px; border-left: 4px solid #007bff; margin-bottom: 5px;">
    <strong style="color: #007bff;">GET</strong> <code>/api/v1/metricas/pagos-caja</code> - Pagos En Caja
  </summary>
  <div style="padding: 15px; border: 1px solid #f8f9fa; border-top: none; margin-bottom: 20px;">
    
    <p><strong>ID de la Operación:</strong> <code>pagos_en_caja_api_v1_metricas_pagos_caja_get</code></p>
    
    <p>Cantidad y monto de items (cuotas, reservas, entradas, compras) marcados como pagados en caja, desglosado por tipo.</p>

    <h3>Respuestas</h3>

    <p><strong>Código:</strong> <code>200 OK</code></p>
    <ul>
      <li><strong>Descripción:</strong> Successful Response</li>
    </ul>
    <div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
  </span><span class="nl">"desglose"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
    </span><span class="p">{</span><span class="w">
      </span><span class="nl">"tipo"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="p">,</span><span class="w">
      </span><span class="nl">"cantidad"</span><span class="p">:</span><span class="w"> </span><span class="mi">0</span><span class="p">,</span><span class="w">
      </span><span class="nl">"monto_total"</span><span class="p">:</span><span class="w"> </span><span class="mf">0.0</span><span class="w">
    </span><span class="p">}</span><span class="w">
  </span><span class="p">],</span><span class="w">
  </span><span class="nl">"total_cantidad"</span><span class="p">:</span><span class="w"> </span><span class="mi">0</span><span class="p">,</span><span class="w">
  </span><span class="nl">"total_monto"</span><span class="p">:</span><span class="w"> </span><span class="mf">0.0</span><span class="w">
</span><span class="p">}</span>
</code></pre></div></div>

    <p><strong>Código:</strong> <code>422 Unprocessable Entity</code></p>
    <ul>
      <li><strong>Descripción:</strong> Validation Error</li>
    </ul>
  </div>
</details>

<details>
  <summary style="font-size: 1.1em; cursor: pointer; padding: 10px; background-color: #f8f9fa; border-radius: 4px; border-left: 4px solid #007bff; margin-bottom: 5px;">
    <strong style="color: #007bff;">GET</strong> <code>/api/v1/metricas/finanzas</code> - Obtener Dashboard Finanzas
  </summary>
  <div style="padding: 15px; border: 1px solid #f8f9fa; border-top: none; margin-bottom: 20px;">
    
    <p><strong>ID de la Operación:</strong> <code>obtener_dashboard_finanzas_api_v1_metricas_finanzas_get</code></p>
    
    <p>Genera la información agregada para el panel de control financiero.</p>

    <h3>Parámetros de consulta (Query Params)</h3>
    <table>
      <thead>
        <tr>
          <th>Nombre</th>
          <th>Tipo</th>
          <th>Obligatorio</th>
          <th>Descripción</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><code>periodo</code></td>
          <td>String</td>
          <td>No</td>
          <td>Formato YYYY-MM. Si no se envía, toma el mes actual.</td>
        </tr>
      </tbody>
    </table>

    <h3>Respuestas</h3>

    <p><strong>Código:</strong> <code>200 OK</code></p>
    <ul>
      <li><strong>Descripción:</strong> Successful Response</li>
    </ul>
    <div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
  </span><span class="nl">"periodo"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="p">,</span><span class="w">
  </span><span class="nl">"recaudacion_total"</span><span class="p">:</span><span class="w"> </span><span class="mf">0.0</span><span class="p">,</span><span class="w">
  </span><span class="nl">"desglose"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
    </span><span class="p">{</span><span class="w">
      </span><span class="nl">"concepto"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="p">,</span><span class="w">
      </span><span class="nl">"monto"</span><span class="p">:</span><span class="w"> </span><span class="mf">0.0</span><span class="w">
    </span><span class="p">}</span><span class="w">
  </span><span class="p">]</span><span class="w">
</span><span class="p">}</span>
</code></pre></div></div>

    <p><strong>Código:</strong> <code>422 Unprocessable Entity</code></p>
    <ul>
      <li><strong>Descripción:</strong> Validation Error</li>
    </ul>
  </div>
</details>

<details>
  <summary style="font-size: 1.1em; cursor: pointer; padding: 10px; background-color: #f8f9fa; border-radius: 4px; border-left: 4px solid #007bff; margin-bottom: 5px;">
    <strong style="color: #007bff;">GET</strong> <code>/api/v1/analiticas/fidelizacion</code> - Obtener Dashboard Fidelizacion
  </summary>
  <div style="padding: 15px; border: 1px solid #f8f9fa; border-top: none; margin-bottom: 20px;">
    
    <p><strong>ID de la Operación:</strong> <code>obtener_dashboard_fidelizacion_api_v1_analiticas_fidelizacion_get</code></p>
    
    <p>Obtiene el dashboard de fidelización con predicciones de morosidad y tendencias.</p>

    <h3>Respuestas</h3>

    <p><strong>Código:</strong> <code>200 OK</code></p>
    <ul>
      <li><strong>Descripción:</strong> Successful Response</li>
    </ul>
    <div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
  </span><span class="nl">"periodo_analizado"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
    </span><span class="nl">"desde"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="p">,</span><span class="w">
    </span><span class="nl">"hasta"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="p">;</span><span class="w">
  </span><span class="p">},</span><span class="w">
  </span><span class="nl">"prediccion_morosidad"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
    </span><span class="p">{</span><span class="w">
      </span><span class="nl">"socio_id"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string (uuid)"</span><span class="p">,</span><span class="w">
      </span><span class="nl">"nombre_completo"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="p">,</span><span class="w">
      </span><span class="nl">"probabilidad_atraso"</span><span class="p">:</span><span class="w"> </span><span class="mf">0.0</span><span class="p">,</span><span class="w">
      </span><span class="nl">"dias_promedio_historico"</span><span class="p">:</span><span class="w"> </span><span class="mf">0.0</span><span class="p">,</span><span class="w">
      </span><span class="nl">"nivel_riesgo"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="w">
    </span><span class="p">}</span><span class="w">
  </span><span class="p">],</span><span class="w">
  </span><span class="nl">"tendencias_pago"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
    </span><span class="p">{</span><span class="w">
      </span><span class="nl">"mes"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="p">,</span><span class="w">
      </span><span class="nl">"a_termino"</span><span class="p">:</span><span class="w"> </span><span class="mi">0</span><span class="p">,</span><span class="w">
      </span><span class="nl">"fuera_de_termino"</span><span class="p">:</span><span class="w"> </span><span class="mi">0</span><span class="w">
    </span><span class="p">}</span><span class="w">
  </span><span class="p">]</span><span class="w">
</span><span class="p">}</span>
</code></pre></div></div>

    <p><strong>Código:</strong> <code>422 Unprocessable Entity</code></p>
    <ul>
      <li><strong>Descripción:</strong> Validation Error</li>
    </ul>
  </div>
</details>
