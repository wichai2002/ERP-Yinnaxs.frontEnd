<template>
    <!-- <div class="row"> col-lg-4 col-md-3 col-sm-2 -->
        <div class="col-2">
            <!-- Toggle button for small screens -->
            <button class="navbar-toggler " type="button" @click="toggleSidebar"  style="color: #FFF;"
            :class="{hiding: isOpen}">
                <span class="navbar-toggler-icon" ></span>
            </button>
            
            <!-- Sidebar style="background-color: #2A3E4C;" -->
            <nav class="sidebar" :class="{ 'sidebar-open': isOpen }" style="background-color: #2A3E4C ;">
                <h1 class="text-center" style="color: #2ECD99; font-weight: 700; ">HRMS</h1>
                <div class="position-sticky py-3">
                    <ul class="nav flex-column mx-3 my-2">
                        <li class="nav-item d-flex justify-content-start">
                            <router-link to="/dashboard" class="nav-link" :class="{ active: isActive('/dashboard') }">
                                <p class="fs-5 fa text-decoration-none wht" :style="{ color: navTextColor('/dashboard') }">
                                    <i class="bi bi-kanban-fill mx-2"></i><span>Dashboard</span>
                                </p>
                            </router-link>

                        </li>
                        <li class="nav-item d-flex justify-content-start">
                            <router-link to="/employees" class="nav-link" :class="{ active: isActive('/employees') }">
                                <p class="fs-5 fa text-decoration-none wht" :style="{ color: navTextColor('/employees') }">
                                    <i class="bi bi-people-fill mx-2"></i><span>Employees</span>
                                </p>
                            </router-link>
                        </li>
                        <li class="nav-item d-flex justify-content-start">
                            <router-link to="/attendence" class="nav-link" :class="{ active: isActive('/attendence') }">
                                <p class="fs-5 fa text-decoration-none wht" :style="{ color: navTextColor('/attendence') }">
                                    <i class="bi bi-alarm-fill mx-2"></i><span>Attendence</span>
                                </p>
                            </router-link>
                        </li>
                        <li class="nav-item d-flex justify-content-start">
                            <router-link to="/leave" class="nav-link" :class="{ active: isActive('/leave') }">
                                <p class="fs-5 fa text-decoration-none wht" :style="{ color: navTextColor('/leave') }">
                                    <i class="bi bi-calendar-week-fill mx-2"></i><span>Leave</span>
                                </p>
                            </router-link>
                        </li>
                        <li class="nav-item d-flex justify-content-start">
                            <router-link to="/payroll" class="nav-link" :class="{ active: isActive('/payroll') }">
                                <p class="fs-5 fa text-decoration-none wht" :style="{ color: navTextColor('/payroll') }">
                                    <i class="bi bi-people-fill mx-2"></i><span>Payroll</span>
                                </p>
                            </router-link>
                        </li>
                        <li class="nav-item d-flex justify-content-start">
                            <router-link to="/training" class="nav-link" :class="{ active: isActive('/training') }">
                                <p class="fs-5 fa text-decoration-none wht" :style="{ color: navTextColor('/training') }">
                                    <i class="bi bi-people-fill mx-2"></i><span>Training</span>
                                </p>
                            </router-link>
                        </li>
                        <li class="nav-item d-flex justify-content-start">
                            <router-link to="/recuitment" class="nav-link" :class="{ active: isActive('/recuitment') }">
                                <p class="fs-5 fa text-decoration-none wht" :style="{ color: navTextColor('/recuitment') }">
                                    <i class="bi bi-people-fill mx-2"></i><span>Recuitment</span>
                                </p>
                            </router-link>
                        </li>
                    </ul>
                </div>
            </nav>
        </div>
    <!-- </div> -->
</template>

<script>
export default {
    data() {
        return {
            isOpen: false,
            
        };
    },
    methods: {
        toggleSidebar() {
            this.isOpen = !this.isOpen;
        },
        isActive(route) {
            return this.$route.path.toLowerCase() === route;
        },
        navTextColor(route) {
            if (this.isActive(route) == true) {
                return "#2A3E4C !important";
            } else {
                return "white !important"
            }
        }
    }
};
</script>

<style scoped>
/* Sidebar styles */
.sidebar {
    position: fixed;

    top: 0;
    bottom: 0;
    left: 0;
    z-index: 1200;
    padding-top: 1.3rem;

    /* Adjust according to your navbar height */
    width: 17.5%;
    background-color: #f8f9fa;
    box-shadow: inset -1px 0 0 rgba(0, 0, 0, .1);
    transition: transform 0.3s ease-in-out, visibility 0.3s;
}
.hiding{
    display: none;
}
.sidebar-open {
    transform: translateX(0);
}

.nav-link.active {
    width: 100%;
    background-color: #e9ecef;
}


/* Responsive styles */
@media (max-width: 768px) {
    .sidebar {
        width: 0;
        visibility: hidden;
    }

    .sidebar-open {
        transform: translateX(-100%);
        visibility: visible;
    }
}

.wht {
    font-weight: 700;
}
</style>
