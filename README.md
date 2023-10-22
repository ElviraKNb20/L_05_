# L_05_
import java.util.ArrayList;
import java.util.List;

public class PublicTransportInfoCenter {
    private List<PublicTransportRoute> routes;

    public PublicTransportInfoCenter() {
        this.routes = new ArrayList<>();
    }

    public void addRoute(String routeName, String startTime, String endTime, double fare) {
        PublicTransportRoute route = new PublicTransportRoute(routeName, startTime, endTime, fare);
        routes.add(route);
    }

    public void displayRoutes() {
        for (PublicTransportRoute route : routes) {
            System.out.println("Route: " + route.getRouteName());
            System.out.println("Start Time: " + route.getStartTime());
            System.out.println("End Time: " + route.getEndTime());
            System.out.println("Fare: " + route.getFare());
            System.out.println();
        }
    }

    // Внутрішній клас для представлення інформації про маршрут
    private class PublicTransportRoute {
        private String routeName;
        private String startTime;
        private String endTime;
        private double fare;

        public PublicTransportRoute(String routeName, String startTime, String endTime, double fare) {
            this.routeName = routeName;
            this.startTime = startTime;
            this.endTime = endTime;
            this.fare = fare;
        }

        public String getRouteName() {
            return routeName;
        }

        public String getStartTime() {
            return startTime;
        }

        public String getEndTime() {
            return endTime;
        }

        public double getFare() {
            return fare;
        }
    }

    public static void main(String[] args) {
        PublicTransportInfoCenter infoCenter = new PublicTransportInfoCenter();
        infoCenter.addRoute("Bus 101", "08:00 AM", "09:30 AM", 2.50);
        infoCenter.addRoute("Tram A", "07:30 AM", "10:00 AM", 1.75);
        infoCenter.displayRoutes();
    }
}
