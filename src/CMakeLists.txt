project(libm)

set(LIB_SOURCES
    e_acos.c
    e_acosf.c
    e_asin.c
    e_asinf.c
    e_atan2.c
    e_exp.c
    e_fmod.c
    e_log.c
    e_pow.c
    e_powf.c
    e_rem_pio2.c
    e_rem_pio2f.c
    e_sqrt.c
    e_sqrtf.c
    k_cos.c
    k_cosf.c
    k_rem_pio2.c
    k_sin.c
    k_sinf.c
    k_tan.c
    k_tanf.c
    s_atan.c
    s_ceil.c
    s_ceilf.c
    s_copysign.c
    s_copysignf.c
    s_cos.c
    s_cosf.c
    s_fabs.c
    s_fabsf.c
    s_floor.c
    s_floorf.c
    s_round.c
    s_scalbn.c
    s_scalbnf.c
    s_sin.c
    s_sinf.c
    s_tan.c
    s_tanf.c
    s_trunc.c
)

set(LIB_HEADERS
    public/math.h
    public/sys/cdefs.h
    math_private.h
)

set(mark3_cc_flags "${mark3_cc_flags} -Wno-unused-variable -Wno-sign-compare -Wno-parentheses -Wno-maybe-uninitialized -Wno-uninitialized")
mark3_add_library_c(libm ${LIB_SOURCES} ${LIB_HEADERS})

target_include_directories(libm
    PUBLIC
        public
    )

target_link_libraries(libm
    libc
)
